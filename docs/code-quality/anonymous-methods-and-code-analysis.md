---
title: 무명 메서드 코드 분석 경고
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- methods, anonymous
- code analysis, anonymous methods
- anonymous methods, code analysis
ms.assetid: bf0a1a9b-b954-4d46-9c0b-cee65330ad00
dev_langs:
- CSharp
- VB
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: dd5053f3774c7a92d16690883a0845ba7bae32db
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55008935"
---
# <a name="anonymous-methods-and-code-analysis"></a>무명 메서드 및 코드 분석

*무명 메서드* 이름이 없는 메서드입니다. 무명 메서드 코드 블록을 대리자 매개 변수로 전달 하도록 가장 자주 사용 됩니다. 이 문서에서는 코드 분석에서 무명 메서드에 대 한 메트릭 및 경고를 처리 하는 방법을 설명 합니다.

## <a name="anonymous-methods-declared-in-a-member"></a>멤버에 선언 된 익명 메서드

경고 및 메트릭은 무명 메서드의 메서드 또는 접근자와 같은 멤버에 선언 된 메서드를 선언 하는 멤버와 연결 됩니다. 메서드를 호출 하는 멤버와 연결 되지 않습니다.

다음 클래스 선언에 있는 모든 경고의 예를 들어 **무명 메서드** 에 대해 발생 시켜야 **Method1** 아니라 **Method2**합니다.

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean

Class AClass
    Sub Method1()
        Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5
        Method2(anonymousMethod)
    End Sub
    Sub Method2(ByVal anonymousMethod As ADelegate)
        anonymousMethod(10)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    void Method1()
    {
        Delegate anonymousMethod = delegate()
        {
          Console.WriteLine("");
        }
        Method2(anonymousMethod);
    }

    void Method2(Delegate anonymousMethod)
    {
        anonymousMethod();
    }
}
```

## <a name="inline-anonymous-methods"></a>인라인 무명 메서드

경고 및 메트릭 필드에 대 한 인라인 할당으로 선언 되는 무명 메서드의 생성자를 사용 하 여 연결 됩니다. 필드로 선언 되 면 `static` (`Shared` Visual basic에서), 경고 및 메트릭 클래스 생성자를 사용 하 여 연결 됩니다. 그렇지 않으면 인스턴스 생성자를 사용 하 여 연결 됩니다.

다음 클래스 선언에 있는 모든 경고의 예를 들어 **anonymousMethod1** 의 암시적으로 생성 된 기본 생성자에 대해 발생 **클래스**합니다. 에 있는 경고 **anonymousMethod2** 암시적으로 생성 된 클래스 생성자에 대해 적용 됩니다.

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean
Class AClass
    Dim anonymousMethod1 As ADelegate = Function(ByVal value As Integer) value > 5
    Shared anonymousMethod2 As ADelegate = Function(ByVal value As Integer) value > 5

    Sub Method1()
        anonymousMethod1(10)
        anonymousMethod2(10)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    Delegate anonymousMethod1 = delegate()
    {
       Console.WriteLine("");
    }

    static Delegate anonymousMethod2 = delegate()
    {
       Console.WriteLine("");
    }

    void Method()
    {
       anonymousMethod1();
       anonymousMethod2();
    }
}
```

클래스는 생성자를 여러 개 지정 된 필드에 값을 할당 하는 인라인 무명 메서드를 포함할 수 있습니다. 이 경우에 경고 및 메트릭 연관 된 모든 생성자는 동일한 클래스의 다른 생성자에 연결 하지 않는 한 합니다.

다음 클래스 선언에 있는 모든 경고의 예를 들어 **무명 메서드** 에 대해 발생 시켜야 **class (int)** 하 고 **Class(string)**, 하지만 대해서가 아니라 **Class()** 합니다.

```vb
Delegate Function ADelegate(ByVal value As Integer) As Boolean

Class AClass

    Dim anonymousMethod As ADelegate = Function(ByVal value As Integer) value > 5

    SubNew()
        New(CStr(Nothing))
    End Sub

    Sub New(ByVal a As Integer)
    End Sub

    Sub New(ByVal a As String)
    End Sub
End Class
```

```csharp
delegate void Delegate();

class Class
{
    Delegate anonymousMethod = delegate()
    {
       Console.WriteLine("");
    }

    Class() : this((string)null)
    {
    }

    Class(int a)
    {
    }

    Class(string a)
    {
    }
}
```

컴파일러는 다른 생성자에 연결 되지 않은 모든 생성자에 대 한 고유한 메서드를 출력 하기 때문에 생성자에 대 한 경고가 발생 합니다. 이 동작으로 인해 모든는에서 위반이 발생 **무명 메서드** 개별적으로 실행 되지 않아야 합니다. 또한 하는 경우 새 생성자가 도입에 대해 이전에 표시 되지 않은 경고 **class (int)** 하 고 **Class(string)** 새 생성자에 대해서도 실행 되지 않아야 합니다.

두 가지 방법 중 하나로이 문제를 해결할 수 있습니다.

- 선언 **무명 메서드** 공용 생성자에서는 모든 생성자 체인입니다.
- 선언 **무명 메서드** 초기화 메서드에서 모든 생성자에 의해 호출 됩니다.

## <a name="see-also"></a>참고자료

- [관리 코드 품질 분석](../code-quality/code-analysis-for-managed-code-overview.md)
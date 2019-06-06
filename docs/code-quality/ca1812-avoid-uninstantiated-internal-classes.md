---
title: 'CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마세요.'
ms.date: 05/16/2019
ms.topic: reference
f1_keywords:
- CA1812
- AvoidUninstantiatedInternalClasses
helpviewer_keywords:
- AvoidUninstantiatedInternalClasses
- CA1812
ms.assetid: 1bb92a42-322a-44cc-98a8-8858212c1e1f
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: a0d55af3c5522c6bb9aa3ad8a023f070c187ca6f
ms.sourcegitcommit: 5483e399f14fb01f528b3b194474778fd6f59fa6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/05/2019
ms.locfileid: "66714260"
---
# <a name="ca1812-avoid-uninstantiated-internal-classes"></a>CA1812: 인스턴스화되지 않은 내부 클래스를 사용하지 마세요.

|||
|-|-|
|TypeName|AvoidUninstantiatedInternalClasses|
|CheckId|CA1812|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

내부 (어셈블리 수준) 형식은 인스턴스화되지 합니다.

## <a name="rule-description"></a>규칙 설명

이 규칙 형식 생성자 중 하나에 대 한 호출을 찾으려고 하 고 호출이 있으면 위반을 보고 합니다.

이 규칙에서 다음 형식은 검사 하지 않습니다.

- 값 형식

- 추상 형식

- 열거형

- 대리자

- 컴파일러에서 내보낸 배열 형식

- 인스턴스화할 수 없습니다만 정의 하는 형식 [ `static` ](/dotnet/csharp/language-reference/keywords/static) ([ `Shared` Visual Basic의](/dotnet/visual-basic/language-reference/modifiers/shared)) 메서드.

적용 하는 경우는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute?displayProperty=fullName> 분석 되는 어셈블리에이 규칙은 플래그 형식으로 표시 된 [ `internal` ](/dotnet/csharp/language-reference/keywords/internal) ([ `Friend` Visual Basic의](/dotnet/visual-basic/language-reference/modifiers/friend)) 필드 일 수 있으므로 friend 어셈블리를 사용합니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하 고, 형식을 제거 또는 사용 하는 코드를 추가 합니다. 형식 포함 되 면 `static` 메서드는 다음 중 하나를 컴파일러가 기본 public 인스턴스 생성자를 내보내는 하지 않도록 하려면 형식에 추가 합니다.

- 합니다 `static` 한정자 C# 대상으로 하는 형식 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 이상.

- .NET Framework 버전 1.0 및 1.1을 대상으로 하는 형식에 대 한 개인 생성자입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 다음과 같은 상황에서이 경고를 표시 하는 것이 좋습니다.

- 클래스가 만들어질 바인딩된 리플렉션 메서드를 통해 같은 <xref:System.Activator.CreateInstance%2A?displayProperty=fullName>합니다.

- 클래스는 런타임 또는 ASP.NET에 의해 자동으로 생성 됩니다. 자동으로 생성된 된 클래스의 예로 구현 하는 <xref:System.Configuration.IConfigurationSectionHandler?displayProperty=fullName> 또는 <xref:System.Web.IHttpHandler?displayProperty=fullName>합니다.

- 클래스는 형식 매개 변수로 전달 되는 [ `new` 제약 조건](/dotnet/csharp/language-reference/keywords/new-constraint)합니다. 다음 예제에서는 규칙 CA1812로 플래그가 지정 됩니다.

    ```csharp
    internal class MyClass
    {
        public DoSomething()
        {
        }
    }
    public class MyGeneric<T> where T : new()
    {
        public T Create()
        {
            return new T();
        }
    }

    MyGeneric<MyClass> mc = new MyGeneric<MyClass>();
    mc.Create();
    ```

## <a name="related-rules"></a>관련된 규칙

- [CA1811: 호출 되지 않는 전용 코드를 방지 합니다.](../code-quality/ca1811-avoid-uncalled-private-code.md)
- [CA1801: 사용 되지 않는 매개 변수를 검토](../code-quality/ca1801-review-unused-parameters.md)
- [CA1804: 사용 되지 않는 로컬 항목을 제거](../code-quality/ca1804-remove-unused-locals.md)
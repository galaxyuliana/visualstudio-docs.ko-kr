---
title: 'CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch하세요.'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- CA2102
- CatchNonClsCompliantExceptionsInGeneralHandlers
helpviewer_keywords:
- CA2102
ms.assetid: bf2df68f-d386-4379-ad9e-930a2c2e930d
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 2f361720f45a24e561ab2a886537bda02c73c006
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55923710"
---
# <a name="ca2102-catch-non-clscompliant-exceptions-in-general-handlers"></a>CA2102: 일반 처리기에서 비 CLSCompliant 예외를 catch하세요.

|||
|-|-|
|TypeName|CatchNonClsCompliantExceptionsInGeneralHandlers|
|CheckId|CA2102|
|범주|Microsoft.Security|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

로 표시 되지 않은 어셈블리의 멤버는 <xref:System.Runtime.CompilerServices.RuntimeCompatibilityAttribute> 되거나 표시 됩니다 `RuntimeCompatibility(WrapNonExceptionThrows = false)` 처리 하는 catch 블록이 포함 <xref:System.Exception?displayProperty=fullName> 바로 뒤의 일반 catch 블록은 포함 하지 않습니다. 이 규칙은 무시 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 어셈블리입니다.

## <a name="rule-description"></a>규칙 설명

처리 하는 catch 블록 <xref:System.Exception> 모든 공용 언어 사양 (CLS) 규격이 예외를 catch 합니다. 그러나 비 CLS 규격이 아닌 예외를 catch 하지 않습니다. 비-CLS 규격 예외가 네이티브 코드에서 또는 Microsoft에 의해 생성 된 관리 코드에서 throw 될 수 있습니다 중간 언어 (MSIL) 어셈블러 합니다. C# 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컴파일러 CLS 규격 예외가 throw 되도록 허용 하지 않습니다 및 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 아닌 CLS 규격이 아닌 예외를 catch 하지 않습니다. Catch 블록의 목적은 모든 예외를 처리할 경우 다음 일반 catch 블록 구문을 사용 합니다.

- C#: `catch {}`

- C + +: `catch(...) {}` 또는 `catch(Object^) {}`

처리 되지 않은 비-CLS 규격 예외가 catch 블록에서 이전에 허용 된 권한 제거 되 면 보안 문제가 됩니다. 비 CLS 규격이 아닌 예외를 발견 하지 및 때문에 비-CLS 규격 예외가 throw 되는 악성 메서드는 높은 권한으로 실행 수 없습니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

모든 catch 하려는 경우이 규칙 위반 문제를 해결 하려면 예외를 대체 또는 일반 catch 블록을 추가 하거나 어셈블리 표시 `RuntimeCompatibility(WrapNonExceptionThrows = true)`합니다. Catch 블록에서 사용 권한을 제거 하는 경우 중복 기능 일반에서 catch 블록입니다. 이 모든 예외를 처리 하려는 경우를 처리 하는 catch 블록으로 바꿉니다 <xref:System.Exception> 특정 예외 형식을 처리 하는 catch 블록을 사용 하 여 합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

Try 블록에는 비-CLS 규격 예외가 발생할 수 있는 모든 문이 없는 경우이 규칙에서 경고를 표시 하지 않아도 안전 합니다. 네이티브 또는 관리 코드는 cls 규격이 아닌 비규격 예외가 throw 할 수 있습니다, 되므로이 try 블록 내의 모든 코드 경로에서 실행 될 수 있는 모든 코드에 대 한 지식이 필요 합니다. 공용 언어 런타임에서 CLS 규격 예외가 throw 되지 않습니다 확인 합니다.

## <a name="example-1"></a>예제 1

다음 예제에서는 CLS 규격 예외가 throw 되는 MSIL 클래스를 보여 줍니다.

```cpp
.assembly ThrowNonClsCompliantException {}
.class public auto ansi beforefieldinit ThrowsExceptions
{
   .method public hidebysig static void
         ThrowNonClsException() cil managed
   {
      .maxstack  1
      IL_0000:  newobj     instance void [mscorlib]System.Object::.ctor()
      IL_0005:  throw
   }
}
```

## <a name="example-2"></a>예제 2

다음 예제에서는 규칙을 충족 하는 일반 catch 블록을 포함 하는 메서드를 보여 줍니다.

[!code-csharp[FxCop.Security.CatchNonClsCompliantException#1](../code-quality/codesnippet/CSharp/ca2102-catch-non-clscompliant-exceptions-in-general-handlers_1.cs)]

다음과 같이 이전 예제를 컴파일하십시오.

```cpp
ilasm /dll ThrowNonClsCompliantException.il
csc /r:ThrowNonClsCompliantException.dll CatchNonClsCompliantException.cs
```

## <a name="related-rules"></a>관련된 규칙

[CA1031: 일반적인 예외 형식을 catch 하지 마십시오.](../code-quality/ca1031-do-not-catch-general-exception-types.md)

## <a name="see-also"></a>참고자료

- [예외 및 예외 처리](/dotnet/csharp/programming-guide/exceptions/exceptions-and-exception-handling)
- [Ilasm.exe(IL 어셈블러)](/dotnet/framework/tools/ilasm-exe-il-assembler)
- [언어 독립성 및 언어 독립적 구성 요소](/dotnet/standard/language-independence-and-language-independent-components)
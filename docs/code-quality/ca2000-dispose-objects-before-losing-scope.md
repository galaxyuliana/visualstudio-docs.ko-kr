---
title: 'CA2000: 범위를 벗어나기 전에 개체를 삭제하세요.'
ms.date: 05/14/2019
ms.topic: reference
f1_keywords:
- CA2000
- Dispose objects before losing scope
- DisposeObjectsBeforeLosingScope
helpviewer_keywords:
- CA2000
- DisposeObjectsBeforeLosingScope
ms.assetid: 0c3d7d8d-b94d-46e8-aa4c-38df632c1463
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
ms.workload:
- multiple
ms.openlocfilehash: 732b3d683802c50042ee40fee1549a9d247e2470
ms.sourcegitcommit: 283f2dbce044a18e9f6ac6398f6fc78e074ec1ed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/16/2019
ms.locfileid: "65804970"
---
# <a name="ca2000-dispose-objects-before-losing-scope"></a>CA2000: 범위를 벗어나기 전에 개체를 삭제하세요.

|||
|-|-|
|TypeName|DisposeObjectsBeforeLosingScope|
|CheckId|CA2000|
|범주|Microsoft.Reliability|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

로컬 개체는 <xref:System.IDisposable> 형식을 만든 다음이 있지만 개체에 대 한 모든 참조가 범위를 벗어나기 전에 개체 삭제 되지 않습니다.

## <a name="rule-description"></a>규칙 설명

모든 참조가 범위를 벗어나기 전에 삭제 가능한 개체를 명시적으로 삭제 되지 않습니다, 경우 개체는 가비지 수집기에서 개체의 종료자를 실행 하는 경우 임의의 시점에 삭제 됩니다. 종료자 수 없게 하는 예외적인 이벤트가 발생할 수 있으므로 실행에서 개체의 개체를 명시적으로 삭제 해야 대신 합니다.

### <a name="special-cases"></a>특별 한 경우

개체 삭제 되지 않습니다 하는 경우에 다음 유형의 로컬 개체에 대 한 규칙 CA2000 발생 하지 않습니다.

- <xref:System.IO.Stream?displayProperty=nameWithType>
- <xref:System.IO.TextReader?displayProperty=nameWithType>
- <xref:System.IO.TextWriter?displayProperty=nameWithType>
- <xref:System.Resources.IResourceReader?displayProperty=nameWithType>

이러한 형식의 개체 생성자에 전달 하 고 다음 필드에 할당을 *소유권 양도 dispose* 새로 생성 된 형식입니다. 즉, 새로 생성된 된 형식의 개체를 삭제 하기 위한 책임 되었습니다. 생성자에 이러한 형식의 개체를 전달 하는 코드를 CA2000 개체에 대 한 모든 참조 하기 전에 삭제 되지 않습니다 하는 경우에 발생 하는 규칙의 위반이 없습니다 경우 범위를 벗어납니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 호출 <xref:System.IDisposable.Dispose%2A> 모든 참조가 범위를 벗어나기 전에 개체에 있습니다.

사용할 수는 [ `using` 문을](/dotnet/csharp/language-reference/keywords/using-statement) ([ `Using` ](/dotnet/visual-basic/language-reference/statements/using-statement) Visual basic에서) 구현 하는 개체를 래핑할 <xref:System.IDisposable>합니다. 이 방식으로 래핑된 개체의 끝에 자동으로 삭제 된 `using` 블록입니다. 그러나 다음과 같은 경우 안 또는 사용 하 여 처리할 수 없습니다.는 `using` 문:

- 삭제 가능한 개체를 반환 하려면 개체에서 구성 해야 합니다는 `try/finally` 외부의 블록을 `using` 블록입니다.

- 삭제 가능한 개체의 생성자에서의 멤버를 초기화 하지 않는 한 `using` 문입니다.

- 하나의 예외 처리기에서 보호 되는 생성자에 중첩 된 경우는 [취득 부분을 `using` 문](/dotnet/csharp/language-reference/language-specification/statements#the-using-statement), 되지 중첩 된 생성자가 만든 개체에서 외부 생성자에서 오류가 발생할 수 있습니다 닫혔습니다. 다음 예제에서는 실패 합니다 <xref:System.IO.StreamReader> 생성자에서 발생할 수 있습니다는 <xref:System.IO.FileStream> 닫히지 않음 개체입니다. CA2000 플래그이 경우 규칙 위반을 지정합니다.

   ```csharp
   using (StreamReader sr = new StreamReader(new FileStream("C:\myfile.txt", FileMode.Create)))
   { ... }
   ```

- 동적 개체의 dispose 패턴을 구현 하는 섀도 개체를 사용 해야 <xref:System.IDisposable> 개체입니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

하지 않는 한이 규칙에서 경고를 숨기지 마십시오.

- 메서드를 호출 하는 개체에서 호출한 `Dispose`와 같은 <xref:System.IO.Stream.Close%2A>
- 경고는 발생 하는 메서드는 <xref:System.IDisposable> 개체를 래핑하는 개체
- 할당 메서드에 dispose 소유권;는 없습니다. 다른 개체 또는 래퍼 메서드에서 만들고 호출자에 게 반환 된 개체를 삭제 해야 전송 되는

## <a name="related-rules"></a>관련된 규칙

- [CA2213: 삭제 가능한 필드는 삭제해야 합니다.](../code-quality/ca2213-disposable-fields-should-be-disposed.md)
- [CA2202: 개체가 여러 번 삭제 하지 마십시오](../code-quality/ca2202-do-not-dispose-objects-multiple-times.md)

## <a name="example"></a>예제

삭제 가능한 개체를 반환 하는 메서드를 구현 하는 경우 개체가 삭제 되 고 있는지 확인 하는 catch 블록 없이 try/finally 블록을 사용 합니다. Try/finally 블록을 사용 하 여 오류 지점에서 발생 하 여 해당 개체가 삭제 되는지 확인 하는 예외를 허용 합니다.

OpenPort1 메서드에서 SomeMethod 위한 호출 또는 ISerializable SerialPort 개체 열기 호출이 실패할 수 있습니다. 이 구현에서 CA2000 경고가 발생 합니다.

OpenPort2 메서드 두 SerialPort 개체에는 null이 선언 된 및로 설정:

- `tempPort`에 테스트 메서드 작업을 수행 하는 데 사용 됩니다.

- `port`메서드의 반환 값에 사용 됩니다.

합니다 `tempPort` 생성 되 고 열을 `try` 블록 및 기타 필요한 동일한 작업을 수행 `try` 블록입니다. 끝에 `try` 열린된 포트 블록에 할당 되는 `port` 반환 되는 개체 및 `tempPort` 개체로 설정 됩니다 `null`합니다.

합니다 `finally` 의 값을 확인 하는 블록 `tempPort`합니다. Null 인 경우 메서드는 작업이 실패 하 고 `tempPort` 모든 리소스가 해제 되도록 닫혀 있습니다. 반환 된 포트 개체는 작업이 실패 한 경우 null 됩니다 메서드의 작업이 성공한 경우 열려 있는 SerialPort 개체를 포함 됩니다.

```csharp
public SerialPort OpenPort1(string portName)
{
   SerialPort port = new SerialPort(portName);
   port.Open();  //CA2000 fires because this might throw
   SomeMethod(); //Other method operations can fail
   return port;
}

public SerialPort OpenPort2(string portName)
{
   SerialPort tempPort = null;
   SerialPort port = null;
   try
   {
      tempPort = new SerialPort(portName);
      tempPort.Open();
      SomeMethod();
      //Add any other methods above this line
      port = tempPort;
      tempPort = null;

   }
   finally
   {
      if (tempPort != null)
      {
         tempPort.Close();
      }
   }
   return port;
}
```

```vb
Public Function OpenPort1(ByVal PortName As String) As SerialPort

   Dim port As New SerialPort(PortName)
   port.Open()    'CA2000 fires because this might throw
   SomeMethod()   'Other method operations can fail
   Return port

End Function

Public Function OpenPort2(ByVal PortName As String) As SerialPort

   Dim tempPort As SerialPort = Nothing
   Dim port As SerialPort = Nothing

   Try
      tempPort = New SerialPort(PortName)
      tempPort.Open()
      SomeMethod()
      'Add any other methods above this line
      port = tempPort
      tempPort = Nothing

   Finally
      If Not tempPort Is Nothing Then
         tempPort.Close()
      End If

   End Try

   Return port

End Function
```

## <a name="example"></a>예제

기본적으로 Visual Basic 컴파일러에는 오버플로 검사 하는 모든 산술 연산자 모든 Visual Basic 산술 연산은 throw 할 수 있습니다 따라서는 <xref:System.OverflowException>합니다. 이 규칙 CA2000 등에서 예기치 않은 위반이 발생할 수 있습니다. 예를 들어, 다음 CreateReader1 함수는 Visual Basic 컴파일러를 표시 하 고 삭제할 필요가 StreamReader를 발생 시키는 예외를 throw 할 수 있는 추가 대 한 지침을 확인 하는 오버플로 때문에 CA2000 위반을 생성 합니다.

이 해결 하려면 프로젝트에서 Visual Basic 컴파일러에서 오버플로 검사를 내보내는 것을 비활성화할 수 있습니다 하거나 다음 CreateReader2 함수와 같이 코드를 수정할 수 있습니다.

오버플로 검사 해제 내보내기를 사용 하지 않으려면 솔루션 탐색기에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 **속성**합니다. 클릭 **컴파일할**, 클릭 **고급 컴파일 옵션**를 확인 하 고 **정수 오버플로 검사 해제**합니다.

[!code-vb[FxCop.Reliability.CA2000.DisposeObjectsBeforeLosingScope#1](../code-quality/codesnippet/VisualBasic/ca2000-dispose-objects-before-losing-scope-vboverflow_1.vb)]

## <a name="see-also"></a>참고자료

- <xref:System.IDisposable>
- [삭제 패턴](/dotnet/standard/design-guidelines/dispose-pattern)
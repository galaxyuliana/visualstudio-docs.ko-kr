---
title: 코드 오류에 대 한 관리 코드 분석 하는 연습 | Microsoft Docs
ms.date: 01/29/2018
ms.topic: conceptual
helpviewer_keywords:
- code analysis [Visual Studio]
- managed code, analyzing
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 3097e52f99f044257b8eaf634455bdf19978d0c3
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55952843"
---
# <a name="walkthrough-analyzing-managed-code-for-code-defects"></a>연습: 코드 오류에 대 한 관리 되는 코드 분석

이 연습에서는 코드 분석 도구를 사용 하 여 코드 오류에 대 한 관리 되는 프로젝트를 분석할 수 있습니다.

이 연습에서는 Microsoft.NET Framework 디자인 지침을 사용 하 여 규칙에 대 한.NET 관리 코드 어셈블리를 분석 하려면 코드 분석을 사용 하는 과정을 안내 합니다.

## <a name="create-a-class-library"></a>클래스 라이브러리 만들기

### <a name="to-create-a-class-library"></a>클래스 라이브러리를 만들려면

1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 차례로 선택합니다.

1. 에 **새 프로젝트** 대화 상자에서 **설치 됨** > **Visual C#** 를 선택한 후 **Windows Desktop**합니다.

1. 선택 된 **클래스 라이브러리 (.NET Framework)** 템플릿.

1. 에 **이름** 텍스트 상자에서 **CodeAnalysisManagedDemo** 을 클릭 한 다음 **확인**합니다.

1. 프로젝트를 만든 후 엽니다는 *Class1.cs* 파일입니다.

1. Class1.cs에서 기존 텍스트를 다음 코드로 바꿉니다.

   ```csharp
   using System;

   namespace testCode
   {
       public class demo : Exception
       {
           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int item { get { return _item; } }
       }
   }
   ```

1. Class1.cs 파일을 저장 합니다.

## <a name="analyze-the-project"></a>프로젝트를 분석 합니다.

### <a name="to-analyze-a-managed-project-for-code-defects"></a>코드 오류에 대 한 관리 되는 프로젝트를 분석 하려면

1. CodeAnalysisManagedDemo 프로젝트에서 선택 **솔루션 탐색기**합니다.

1. **프로젝트** 메뉴에서 **속성**을 클릭합니다.

     CodeAnalysisManagedDemo 속성 페이지가 표시 됩니다.

1. 선택 된 **코드 분석** 탭 합니다.

1. 했는지 **빌드에 코드 분석 사용** 확인란이 선택 되어 있습니다.

1. **이 규칙 집합 실행** 드롭 다운 목록에서 **Microsoft 모든 규칙**합니다.

1. 에 **파일** 메뉴에서 클릭 **선택한 항목 저장**, 한 다음 속성 페이지를 닫습니다.

1. 에 **빌드** 메뉴에서 클릭 **빌드 CodeAnalysisManagedDemo**합니다.

    CodeAnalysisManagedDemo 프로젝트 빌드 경고에 표시 되는 **오류 목록** 하 고 **출력** windows.

## <a name="correct-the-code-analysis-issues"></a>코드 분석 문제 해결

### <a name="to-correct-code-analysis-rule-violations"></a>코드 분석 규칙 위반을 수정 하려면

1. 에 **뷰** 메뉴 선택 **오류 목록**합니다.

    가리키도록 해야 선택한 개발자 프로필에 따라 **다른 Windows** 에 **뷰** 메뉴를 선택한 후 **오류 목록**합니다.

1. **솔루션 탐색기**에서 **모든 파일 표시**를 선택합니다.

1. 속성 노드를 확장 한 다음 엽니다는 *AssemblyInfo.cs* 파일입니다.

1. 경고를 해결 하려면 다음 팁을 사용 합니다.

   [CA1014: CLSCompliantAttribute로 어셈블리 표시](../code-quality/ca1014-mark-assemblies-with-clscompliantattribute.md): Microsoft.Design: '데모'를 CLSCompliantAttribute로 표시 되어야 합니다 하 고 해당 값은 true 여야 합니다.

   1. 코드를 추가 `using System;` AssemblyInfo.cs 파일에 있습니다.

   1. 다음으로 코드를 추가 `[assembly: CLSCompliant(true)]` AssemblyInfo.cs 파일의 끝에 있습니다.

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: 이 클래스에 다음 생성자를 추가 합니다: 공용 demo(String)

   1. 생성자를 추가 합니다 `public demo (String s) : base(s) { }` 클래스에 `demo`입니다.

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: 이 클래스에 다음 생성자를 추가 합니다: 공용 데모 (String, 예외)

   1. 생성자를 추가 합니다 `public demo (String s, Exception e) : base(s, e) { }` 클래스에 `demo`입니다.

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: 이 클래스에 다음 생성자를 추가 합니다: 데모 (SerializationInfo, StreamingContext) 보호

   1. 코드를 추가 `using System.Runtime.Serialization;` Class1.cs 파일의 시작 부분에 있습니다.

   1. 그런 다음 생성자를 추가 `protected demo (SerializationInfo info, StreamingContext context) : base(info, context) { } to the class demo.`

   [CA1032: 표준 예외 생성자를 구현](../code-quality/ca1032-implement-standard-exception-constructors.md): Microsoft.Design: 이 클래스에 다음 생성자를 추가 합니다: 공용 demo()

   1. 생성자를 추가 합니다 `public demo () : base() { }` 클래스에 `demo` **합니다.**

   [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: 'TestCode'로 변경 하 여 네임 스페이스 이름 'testCode'의 대/소문자를 수정 합니다.

   1. 네임 스페이스의 대/소문자를 변경 `testCode` 에 `TestCode`입니다.

   [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: 형식 이름 '데모'의 대/소문자를 '데모'로 변경 하 여 수정 합니다.

   1. 멤버의 이름을 변경 `Demo`합니다.

   [CA1709: 식별자에는 올바르게 표기를 사용 해야](../code-quality/ca1709-identifiers-should-be-cased-correctly.md): Microsoft.Naming: 'Item'로 변경 하 여 멤버 이름 'item'의 대/소문자를 수정 합니다.

   1. 멤버의 이름을 변경 `Item`합니다.

   [CA1710: 식별자에는 올바른 접미사를 사용 해야 합니다.](../code-quality/ca1710-identifiers-should-have-correct-suffix.md): Microsoft.Naming: 'Exception'에서 end 'testCode.demo를'의 이름을 바꿉니다.

   1. 클래스 및 해당 생성자의 이름을 변경 `DemoException`합니다.

   [CA2210: 어셈블리에는 올바른 강력한 이름을 사용 해야 합니다.](../code-quality/ca2210-assemblies-should-have-valid-strong-names.md): 'CodeAnalysisManagedDemo' 강력한 이름 키를 사용 하 여 로그인 합니다.

   1. 에 **프로젝트** 메뉴 선택 **CodeAnalysisManagedDemo 속성**합니다.

      프로젝트 속성이 표시 됩니다.

   1. **서명** 탭을 선택합니다.

   1. 선택 된 **어셈블리에 서명할** 확인란 합니다.

   1. 에 **강력한 이름 키 파일 선택** 목록에서  **\<새로 만들기... >** 합니다.

      합니다 **강력한 이름 키 만들기** 대화 상자가 나타납니다.

   1. 에 **키 파일 이름**, TestKey를 입력 합니다.

   1. 암호를 입력 하 고 선택한 **확인**합니다.

   1. 에 **파일** 메뉴 선택 **선택한 항목 저장**, 한 다음 속성 페이지를 닫습니다.

   [CA2237: SerializableAttribute로 ISerializable 형식 표시](../code-quality/ca2237-mark-iserializable-types-with-serializableattribute.md): Microsoft.Usage: 이 형식이 ISerializable을 구현 하는 대로 '데모'를 입력 [Serializable] 특성을 추가 합니다.

   1. 추가 된 `[Serializable ()]` 특성을 클래스 `demo`합니다.

   변경을 완료한 후 Class1.cs 파일은 다음과 같습니다.

   ```csharp
   using System;
   using System.Runtime.Serialization;

   namespace TestCode
   {
       [Serializable()]
       public class DemoException : Exception
       {
           public DemoException () : base() { }
           public DemoException(String s) : base(s) { }
           public DemoException(String s, Exception e) : base(s, e) { }
           protected DemoException(SerializationInfo info, StreamingContext context) : base(info, context) { }

           public static void Initialize(int size) { }
           protected static readonly int _item;
           public static int Item { get { return _item; } }
       }
   }
   ```

1. 프로젝트를 다시 빌드합니다.

## <a name="exclude-code-analysis-warnings"></a>코드 분석 경고를 제외 합니다.

1. 나머지 경고 각각에 대해 다음을 수행합니다.

    1. 경고를 선택 합니다 **오류 목록**합니다.

    1. 마우스 오른쪽 단추 클릭 메뉴 (상황에 맞는 메뉴)에서 선택 **표시 안 함** > **억제 파일에**입니다.

1. 프로젝트를 다시 빌드합니다.

     프로젝트 경고 또는 오류 없이 빌드됩니다.

## <a name="see-also"></a>참고자료

[관리 코드에 대 한 코드 분석](../code-quality/code-analysis-for-managed-code-overview.md)
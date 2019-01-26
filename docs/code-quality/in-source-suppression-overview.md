---
title: 코드 분석 경고 표시 안 함
ms.date: 12/01/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- source suppression, code analysis
- code analysis, source suppression
author: gewarren
ms.author: gewarren
manager: jillfra
dev_langs:
- CSharp
- VB
- CPP
ms.workload:
- multiple
ms.openlocfilehash: 7fd2d8323a249771357ca0b32dc3106f11d8aa1b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55036188"
---
# <a name="suppress-code-analysis-warnings"></a>코드 분석 경고 표시 안 함

경고가 적용 되지 않았음을 나타내는 하는 것이 유용 합니다. 이 코드를 검토 하 고 경고를 표시 하지 않을 수 있는 팀 멤버를 나타냅니다. 소스 비 표시 오류 (ISS) 사용 하는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 경고를 표시 하는 특성입니다. 경고를 생성 하는 코드 세그먼트에 가까운 특성을 배치할 수 있습니다. 추가할 수 있습니다는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 을 입력 하 여 특성을 소스 파일에 경고의 바로 가기 메뉴를 사용할 수 있습니다 합니다 **오류 목록** 자동으로 추가 합니다.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성이 컴파일 시간에 CODE_ANALYSIS 컴파일 기호가 정의 된 경우에 관리 코드 어셈블리의 IL 메타 데이터에 포함 된 조건부 특성입니다.

C + + CLI CA 매크로 사용 하 여\_표시 안 함\_메시지나 CA\_GLOBAL\_SUPPRESS_MESSAGE 헤더 파일에 특성을 추가 합니다.

> [!NOTE]
> 소스에서 메타 데이터를 실수로 전달 하지 않으려면-소스 비 표시 오류 릴리스 빌드에 하지 사용 해야 합니다. 또한 소스에서의 처리 비용으로 인해 응용 프로그램의 성능이 저하 될 수 있습니다.

> [!NOTE]
> Visual Studio 2017로 프로젝트를 마이그레이션하는 경우 많은 수의 코드 분석 경고를 사용 하 여 직면 갑자기 수 있습니다. 이러한 경고에서 들어온 [Roslyn 분석기](roslyn-analyzers-overview.md)합니다. 경고를 해결할 준비가 아닌 경우 억제할 수 있습니다 모두 선택 하 여 **분석** > **코드 분석 실행 및 활성 문제를 표시 하지 않으려면**합니다.
>
> ![코드 분석을 실행 하 고 Visual Studio의 문제를 표시 하지 않으려면](media/suppress-active-issues.png)

## <a name="suppressmessage-attribute"></a>SuppressMessage 특성

선택 하는 경우 **Suppress** 에서 코드 분석 경고를 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서를 **오류 목록**, <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 프로젝트의 전역 비 표시 오류 또는 코드에서 특성이 추가 됩니다 파일입니다.

<xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성 형식은 다음과 같습니다.

```vb
<Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")>
```

```csharp
[Scope:SuppressMessage("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")]
```

```cpp
CA_SUPPRESS_MESSAGE("Rule Category", "Rule Id", Justification = "Justification", MessageId = "MessageId", Scope = "Scope", Target = "Target")
```

특성의 속성은 다음과 같습니다.

- **범주** -규칙이 정의 된 범주입니다. 코드 분석 규칙 범주에 대 한 자세한 내용은 참조 하세요. [관리 코드 경고](../code-quality/code-analysis-for-managed-code-warnings.md)합니다.

- **CheckId** -규칙의 식별자입니다. 지원 규칙 식별자에 대 한 단기 및 장기 이름을 둘 다 포함 됩니다. 짧은 이름은 CAXXXX; 긴 이름은 CAXXXX:FriendlyTypeName입니다.

- **근거** -메시지를 표시 하지 않는 이유를 문서화 하는 데 사용 되는 텍스트입니다.

- **MessageId** -각 메시지에 대 한 문제의 고유 식별자입니다.

- **범위** -경고가 표시 되는 대상입니다. 대상 지정 하지 않으면, 대상 특성으로 설정 됩니다. 지원 [범위](xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope) 다음과 같습니다.

   - `module`

   - `resource`

   - `type`

   - `member`

   - `namespace` -이 범위에는 자체 네임 스페이스에 대해 경고를 하지 않습니다. 네임 스페이스 내의 형식에 대 한 경고를 억제 하지는 않습니다.

   - `namespaceanddescendants` -(New에 대 한 Visual Studio 2019)이이 범위를 표시 하지 않습니다 네임 스페이스 및 해당 하위 모든 기호는 경고입니다. `namespaceanddescendants` 값 Roslyn 분석기에만 유효 하 고 이진, FxCop 기반 정적 분석에서 무시 됩니다.

- **대상** -경고가 표시 되는 대상을 지정 하는 데 사용 되는 식별자입니다. 정규화 된 항목 이름을 포함 해야 합니다.

## <a name="suppressmessage-usage"></a>SuppressMessage 사용

코드 분석 경고는 수준에 표시 되지 않습니다는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성은 적용 됩니다. 예를 들어, 어셈블리, 모듈, 형식, 멤버 또는 매개 변수 수준에서 특성을 적용할 수 있습니다. 이 목적은 위반이 발생 하는 코드에 표시 안 함 정보를 하는 것입니다.

비 표시의 일반적인 형식은 규칙 범주와 규칙 이름의 선택적 읽을 표현을 포함 하는 규칙 식별자가 포함 됩니다. 예를 들어:

`[SuppressMessage("Microsoft.Design", "CA1039:ListsAreStrongTyped")]`

소스에서 메타 데이터를 최소화 하기 위한 엄격한 성능상의 이유로 경우 규칙 이름을 생략할 수 있습니다. 규칙 범주 및 해당 규칙 ID 만으로도 충분히 고유 규칙 식별자가 있습니다. 예를 들어:

`[SuppressMessage("Microsoft.Design", "CA1039")]`

유지 관리 용이성을 위해 규칙 이름을 생략 권장 되지 않습니다.

## <a name="suppress-selective-violations-within-a-method-body"></a>메서드 본문 내에서 선택적 위반 표시 안 함

제거 특성 메서드에 적용할 수 있지만 메서드 본문 안에 포함할 수 없습니다. 즉, 모든 위반의 특정 규칙을 추가 하는 경우 표시 되지 않습니다는 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성을 메서드에 있습니다.

경우에 따라 향후 코드를 자동으로 코드 분석 규칙에서 제외 되지 않습니다 있도록 예를 들어 위반의 특정 인스턴스를 표시 하지는 것이 좋습니다. 특정 코드 분석 규칙을 사용 하면 사용 하 여이 작업을 수행 하는 `MessageId` 의 속성을 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성입니다. 레거시 규칙을 특정 기호 (지역 변수 또는 매개 변수) 측면에서 위반에 대 한 일반적으로 `MessageId` 속성입니다. [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md) 은 이러한 규칙의 예입니다. 그러나 실행 코드 (비 기호)에 위반에 대 한 레거시 규칙을 적용 하지 않는 `MessageId` 속성입니다. 또한.NET 컴파일러 플랫폼 ("Roslyn") 분석기 고려 하지 않는 `MessageId` 속성입니다.

규칙의 위반 하 게 특정 기호를 표시 하지 않으려면 기호 이름을 지정 합니다 `MessageId` 의 속성을 <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute> 특성. 다음 예제에서는 두 위반을 사용 하 여 코드를 보여 줍니다. [CA1500:VariableNamesShouldNotMatchFieldNames](../code-quality/ca1500-variable-names-should-not-match-field-names.md)&mdash;에 대 한 합니다 `name` 변수와 대 한 하나는 `age` 변수. 에 대 한 위반만는 `age` 기호를 표시 하지 않습니다.

```vb
Public Class Animal
    Dim age As Integer
    Dim name As String

    <CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId:="age")>
    Sub PrintInfo()
        Dim age As Integer = 5
        Dim name As String = "Charlie"

        Console.WriteLine("Age {0}, Name {1}", age, name)
    End Sub

End Class
```

```csharp
public class Animal
{
    int age;
    string name;

    [System.Diagnostics.CodeAnalysis.SuppressMessage("Microsoft.Maintainability", "CA1500:VariableNamesShouldNotMatchFieldNames", MessageId = "age")]
    private void PrintInfo()
    {
        int age = 5;
        string name = "Charlie";

        Console.WriteLine($"Age {age}, Name {name}");
    }
}
```

## <a name="generated-code"></a>생성 된 코드

관리 코드 컴파일러 및 일부 타사 도구는 신속한 코드 개발을 용이 하 게 코드를 생성 합니다. 소스 파일에 표시 되는 컴파일러에서 생성 된 코드는 일반적으로 표시 된 `GeneratedCodeAttribute` 특성입니다.

코드 분석 경고 및 생성 된 코드에 대 한 오류를 표시 하지 않을 것인지를 선택할 수 있습니다. 이러한 경고 및 오류를 표시 하지 않는 방법에 대 한 정보를 참조 하세요. [방법: 생성 된 코드에 대 한 경고를 표시 하지 않으려면](../code-quality/how-to-suppress-code-analysis-warnings-for-generated-code.md)합니다.

> [!NOTE]
> 코드 분석에서 무시 `GeneratedCodeAttribute` 전체 어셈블리 또는 단일 매개 변수 중 하나에 적용 됩니다.

## <a name="global-level-suppressions"></a>전역 수준 비 표시 오류

관리 코드 분석 도구를 사용 하는 검사 `SuppressMessage` 어셈블리, 모듈, 형식, 멤버 또는 매개 변수 수준에서 적용 되는 특성입니다. 리소스 및 네임 스페이스에 대 한 위반을 발생 시킵니다. 이러한 위반은 전역 수준에서 적용 해야 합니다는 범위 및 대상으로 합니다. 예를 들어, 다음과 같은 메시지가 표시는 네임 스페이스 위반을 하지 않습니다.

`[module: SuppressMessage("Microsoft.Design", "CA1020:AvoidNamespacesWithFewTypes", Scope = "namespace", Target = "MyNamespace")]`

> [!NOTE]
> 사용 하 여 경고를 표시 하는 경우 `namespace` 범위 자체는 네임 스페이스에 대해 경고를 억제 합니다. 네임 스페이스 내의 형식에 대 한 경고를 표시 하지 않습니다.

명시적 범위를 지정 하 여 모든 비 표시 오류를 나타낼 수 있습니다. 이러한 비 표시이 오류 전역 수준에 있어야 합니다. 멤버 수준 비 표시 오류 형식을 데코 레이트 하 여 지정할 수 없습니다.

전역 수준 비 표시 오류는 유일한 방법은 명시적으로 제공 되는 사용자 소스에 매핑되지 않는 컴파일러에서 생성 된 코드를 참조 하는 메시지가 표시 되지 않습니다. 예를 들어, 다음 코드는 컴파일러에서 내보낸 생성자에 대 한 위반을 표시 하지 않습니다.

`[module: SuppressMessage("Microsoft.Design", "CA1055:AbstractTypesDoNotHavePublicConstructors", Scope="member", Target="Microsoft.Tools.FxCop.Type..ctor()")]`

> [!NOTE]
> `Target` 항상 정규화 된 항목 이름이 포함 됩니다.

## <a name="global-suppression-file"></a>전역 비 표시 오류 파일

전역 비 표시 오류 파일에 비 표시 오류는 전역 수준 비 표시 오류 또는 대상을 지정 하지 않는 비 표시 오류는 유지 관리 합니다. 예를 들어, 어셈블리 수준 위반에 대해가이 파일에 저장 됩니다. 또한 일부 ASP.NET 비 표시 오류는 프로젝트 수준 설정 양식 뒤에 있는 코드에 사용할 수 없기 때문에이 파일에 저장 됩니다. 전역 비 표시 오류 파일이 생성 되어 처음 선택 하면 프로젝트에 추가 합니다 **프로젝트 비 표시 오류 파일의** 옵션을 합니다 **표시 안 함** 명령을 **오류 목록**창.

## <a name="see-also"></a>참고자료

- <xref:System.Diagnostics.CodeAnalysis.SuppressMessageAttribute.Scope>
- <xref:System.Diagnostics.CodeAnalysis>
- [Roslyn 분석기를 사용 합니다.](../code-quality/use-roslyn-analyzers.md)
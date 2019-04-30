---
title: 텍스트 템플릿에서 모델에 액세스
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, accessing models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: c639ecc19f99f25fb5cb38539d2322131ddc2e0c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63446331"
---
# <a name="accessing-models-from-text-templates"></a>텍스트 템플릿에서 모델에 액세스
텍스트 템플릿을 사용 하 여 보고서 파일, 소스 코드 파일 및 도메인 특정 언어 모델을 기반으로 하는 기타 텍스트 파일을 만들 수 있습니다. 텍스트 템플릿에 대 한 기본 정보를 참조 하세요. [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)합니다. 텍스트 템플릿 DSL을 디버깅할 때 실험적 모드에서 작동 하 고 DSL를 배포한 컴퓨터 에서도 작동 합니다.

> [!NOTE]
> 샘플 텍스트 템플릿은 DSL 솔루션을 만들 때  **\*.tt** 디버깅 프로젝트에 파일이 생성 됩니다. 도메인 클래스의 이름으로 변경 하면 이러한 템플릿은 더 이상 작동 합니다. 그럼에도 불구 하 고 필요한 기본 지시문을 포함 하며 DSL에 맞게 업데이트할 수 있는 예제를 제공 합니다.

 텍스트 템플릿에서 모델 액세스:

- 템플릿 지시문의 상속 속성을 설정 <xref:Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation>합니다. 이 저장소에 대 한 액세스를 제공합니다.

- 액세스 하려는 DSL에 대 한 지시문 프로세서를 지정 합니다. 이 텍스트 템플릿의 코드에서 해당 도메인 클래스, 속성 및 관계를 사용할 수 있도록 DSL에 대 한 어셈블리를 로드 합니다. 또한 지정 된 모델 파일을 로드 합니다.

  `.tt` 최소 언어 DSL 템플릿에서 새 Visual Studio 솔루션을 만들 때 디버깅 프로젝트에 다음 예제와 비슷한 파일이 만들어집니다.

```
<#@ template inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
<#@ output extension=".txt" #>
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>

This text will be output directly.

This is the name of the model: <#= this.ModelRoot.Name #>

Here is a list of elements in the model:
<#
  // When you change the DSL Definition, some of the code below may not work.
  foreach (ExampleElement element in this.ExampleModel.Elements)
  {#>
<#= element.Name #>
<#
  }
#>
```

 이 템플릿에 대 한 다음 사항에 유의 합니다.

- 도메인 클래스, 속성 및 관계 DSL 정의에 정의 된 템플릿을 사용할 수 있습니다.

- 서식 파일에 지정 된 모델 파일을 로드 합니다 `requires` 속성입니다.

- 속성에서 `this` 루트 요소를 포함 합니다. 여기에서 코드 모델의 다른 요소와 이동할 수 있습니다. 속성의 이름은 일반적으로 DSL의 루트 도메인 클래스와 동일 합니다. 이 예제에서는 `this.ExampleModel`입니다.

- 코드 조각을 작성 되는 언어는 C#, 하지만 모든 종류의 텍스트를 생성할 수 있습니다. 또는 코드를 작성할 수 있습니다 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 속성을 추가 하 여 `language="VB"` 에 `template` 지시문입니다.

- 서식 파일을 디버깅 하려면 추가 `debug="true"` 에 `template` 지시문입니다. 예외가 발생 하는 경우에 템플릿을 Visual Studio의 다른 인스턴스에서 열립니다. 코드에서 특정 지점에서 디버거를 중단 하려는 경우 insert 문 `System.Diagnostics.Debugger.Break();`

   자세한 내용은 [T4 텍스트 템플릿 디버깅](../modeling/debugging-a-t4-text-template.md)합니다.

## <a name="about-the-dsl-directive-processor"></a>DSL 지시문 프로세서에 대 한
 템플릿은 DSL 정의에 정의 된 도메인 클래스를 사용할 수 있습니다. 서식 파일의 시작 부분에 일반적으로 나타나는 지시문에 대 한이 상태로 만듭니다. 이전 예제에서는 다음과 같습니다.

```
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1'" #>
```

 지시문의 이름 ( `MyLanguage`,이 예에서) DSL의 이름에서 파생 됩니다. 호출을 *지시문 프로세서* DSL의 일부로 생성 됩니다. 해당 소스 코드를 찾을 수 있습니다 **Dsl\GeneratedCode\DirectiveProcessor.cs**합니다.

 DSL 지시문 프로세서는 두 가지 주요 작업을 수행합니다.

- 효과적으로 DSL을 참조 하는 서식 파일에 어셈블리 및 import 지시문을 삽입 합니다. 이렇게 하면 템플릿 코드에서 도메인 클래스를 사용할 수 있습니다.

- 지정 하는 파일을 로드를 `requires` 매개 변수 속성을 설정 하 고 `this` 참조 하는 로드 된 모델의 루트 요소입니다.

## <a name="validating-the-model-before-running-the-template"></a>서식 파일을 실행 하기 전에 모델 유효성 검사
 템플릿 실행 되기 전에 유효성을 검사 하려면 모델을 발생할 수 있습니다.

```
<#@ MyLanguage processor="MyLanguageDirectiveProcessor" requires="fileName='Sample.myDsl1';validation='open|load|save|menu'" #>
```

 다음 사항을 참고하세요.

1. 합니다 `filename` 및 `validation` 매개 변수는 사용 하 여 구분 ";"이 고 다른 구분 기호 또는 공백 이어야 합니다.

2. 유효성 검사 범주 목록 유효성 검사 메서드를 실행할 수를 결정 합니다. 여러 범주를 사용 하 여 구분 해야 "&#124;"이 고 다른 구분 기호 또는 공백 이어야 합니다.

   오류가 있으면 오류 창에 보고 됩니다 하 고 결과 파일에는 오류 메시지가 포함 됩니다.

## <a name="Multiple"></a> 텍스트 템플릿에서 여러 모델에 액세스

> [!NOTE]
> 이 메서드는 동일한 템플릿에서 여러 모델을 읽을 수 있지만 ModelBus 참조를 지원 하지 않습니다. ModelBus 참조 하 여 상호 연결 하는 모델, 참조 [텍스트 템플릿에서 Visual Studio ModelBus를 사용 하 여](../modeling/using-visual-studio-modelbus-in-a-text-template.md)입니다.

 동일한 텍스트 템플릿에서 둘 이상의 모델에 액세스 하려는 경우 호출 해야 생성 된 지시문 프로세서 번 각 모델에 대 한 합니다. 각 모델의 파일 이름을 지정 해야 합니다 `requires` 매개 변수입니다. 루트 도메인 클래스에 대 한 사용 하려는 이름을 지정 해야 합니다 `provides` 매개 변수입니다. 에 대 한 다른 값을 지정 해야 합니다 `provides` 지시문 호출은 각 매개 변수입니다. 예를 들어, 세 가지 모델 파일이 Library.xyz, School.xyz, 및 Work.xyz 있다고 가정 합니다. 동일한 텍스트 템플릿에서 이들 항목에 액세스 하려면 다음과 유사한 세 가지 지시문 호출을 작성 해야 합니다.

```
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Library.xyz'" provides="ExampleModel=LibraryModel" #>
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='School.xyz'" provides="ExampleModel=SchoolModel" #>
<#@ ExampleModel processor="<YourLanguageName>DirectiveProcessor" requires="fileName='Work.xyz'" provides="ExampleModel=WorkModel" #>
```

> [!NOTE]
> 이 예제 코드는 최소 언어 솔루션 템플릿을 기반으로 하는 언어입니다.

 텍스트 템플릿에서 모델에 액세스 하려면 다음 예제에서 이제 코드와 유사한 코드를 작성할 수 있습니다.

```csharp
<#
foreach (ExampleElement element in this.LibraryModel.Elements)
...
foreach (ExampleElement element in this.SchoolModel.Elements)
...
foreach (ExampleElement element in this.WorkModel.Elements)
...
#>
```

```vb
<#
For Each element As ExampleElement In Me.LibraryModel.Elements
...
For Each element As ExampleElement In Me.SchoolModel.Elements
...
For Each element As ExampleElement In Me.WorkModel.Elements
...
#>
```

## <a name="loading-models-dynamically"></a>모델을 동적으로 로드
 런타임 시 로드 하는 모델을 확인 하려는 경우 동적으로 DSL 별 지시문을 사용 하는 대신, 프로그램 코드에서 모델 파일을 로드할 수 있습니다.

 그러나 DSL 별 지시문의 함수 중 하나 가져오는 것 DSL 네임 스페이스 템플릿 코드는 DSL에서 정의 된 도메인 클래스를 사용할 수 있도록입니다. 지시문을 사용 하지 않는 때문에 추가 해야 합니다  **\<어셈블리 >** 하 고  **\<가져올 >** 로드할 수 있는 모든 모델에 대 한 지시문입니다. 로드할 수 있는 다양 한 모델에 동일한 DSL의 인스턴스인 모든 경우에 간단한 작업입니다.

 파일을 로드 하는 가장 효과적인 방법 Visual Studio ModelBus를 사용 하면 됩니다. 일반적인 시나리오에서는 텍스트 템플릿에 일반적인 방법으로 첫 번째 모델을 로드 하려면 DSL 별 지시문을 사용 합니다. 해당 모델에는 다른 모델에 대 한 ModelBus 참조 포함 됩니다. ModelBus 참조 되는 모델을 열고 특정 요소에 액세스를 사용할 수 있습니다. 자세한 내용은 [텍스트 템플릿에서 Visual Studio ModelBus를 사용 하 여](../modeling/using-visual-studio-modelbus-in-a-text-template.md)입니다.

 덜 일반적인 시나리오를 파일 이름에만 권한이 있는 모델 파일을 여는 현재 Visual Studio 프로젝트에서 되지 않을 수 있습니다. 에 설명 된 기술을 사용 하 여 파일을 열 수는 예제의 경우 [방법: 프로그램 코드로 파일에서 모델 열기](../modeling/how-to-open-a-model-from-file-in-program-code.md)합니다.

## <a name="generating-multiple-files-from-a-template"></a>템플릿에서 여러 파일을 생성합니다.
 -여러 파일을 생성 하려는 경우 예를 들어 모델에서 각 요소에 대 한 별도 파일을 생성 하려면 몇 가지가 있습니다 가능 합니다. 기본적으로 각 템플릿 파일에서 파일을 하나만 생성 됩니다.

### <a name="splitting-a-long-file"></a>긴 파일 분
 이 메서드는 템플릿을 사용 하 여 구분 기호로 구분 된 단일 파일을 생성 합니다. 파일의 부분으로 분할 합니다. 다른 분할 및 단일 파일을 생성 하는 두 가지 템플릿이 있습니다.

 **LoopTemplate.t4** 긴 단일 파일을 생성 합니다. 이 처리 되지 않도록 클릭할 때 직접 때문에 파일 확장명이 ".t4" 것을 확인할 **모든 템플릿 변환**합니다. 이 템플릿은 세그먼트를 구분 하는 구분 기호 문자열을 지정 하는 매개 변수를 사용 합니다.

```
<#@ template ninherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation" #>
<#@ parameter name="delimiter" type="System.String" #>
<#@ output extension=".txt" #>
<#@ MyDSL processor="MyDSLDirectiveProcessor" requires="fileName='SampleModel.mydsl1';validation='open|load|save|menu'" #>
<#
  // Create a file segment for each element:
  foreach (ExampleElement element in this.ExampleModel.Elements)
  {
    // First item is the delimiter:
#>
<#= string.Format(delimiter, element.Id) #>

   Element: <#= element.Name #>
<#
   // Here you generate more content derived from the element.
  }
#>
```

 `LoopSplitter.tt` 호출 `LoopTemplate.t4`, 그런 다음 해당 세그먼트로 결과 파일을 분할 합니다. 모델을 읽지 못하는 때문에이 템플릿에 모델링 템플릿으로 되도록 되어 있지 않습니다 확인 합니다.

```
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="Microsoft.VisualStudio.TextTemplating" #>
<#@ import namespace="System.Runtime.Remoting.Messaging" #>
<#@ import namespace="System.IO" #>

<#
  // Get the local path:
  string itemTemplatePath = this.Host.ResolvePath("LoopTemplate.t4");
  string dir = Path.GetDirectoryName(itemTemplatePath);

  // Get the template for generating each file:
  string loopTemplate = File.ReadAllText(itemTemplatePath);

  Engine engine = new Engine();

  // Pass parameter to new template:
  string delimiterGuid = Guid.NewGuid().ToString();
  string delimiter = "::::" + delimiterGuid + ":::";
  CallContext.LogicalSetData("delimiter", delimiter + "{0}:::");
  string joinedFiles = engine.ProcessTemplate(loopTemplate, this.Host);

  string [] separateFiles = joinedFiles.Split(new string [] {delimiter}, StringSplitOptions.None);

  foreach (string nameAndFile in separateFiles)
  {
     if (string.IsNullOrWhiteSpace(nameAndFile)) continue;
     string[] parts = nameAndFile.Split(new string[]{":::"}, 2, StringSplitOptions.None);
     if (parts.Length < 2) continue;
#>
 Generate: [<#= dir #>] [<#= parts[0] #>]
<#
     // Generate a file from this item:
     File.WriteAllText(Path.Combine(dir, parts[0] + ".txt"), parts[1]);
  }
#>
```
---
title: '연습: 모델에 액세스 하는 텍스트 템플릿 디버그 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: af46a7fe-6b98-4d3d-b816-0bbf8e81e220
caps.latest.revision: 8
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 26ff566c9d9ff833a92668d06c818245ed55d066
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65700579"
---
# <a name="walkthrough-debugging-a-text-template-that-accesses-a-model"></a>연습: 모델에 액세스 하는 텍스트 템플릿 디버그
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

수정 하거나 도메인별 언어 솔루션에서 텍스트 템플릿을 추가 하는 경우 엔진은 소스 코드 또는 생성 된 코드를 컴파일할 때 템플릿을 변환 하는 경우 오류가 발생할 수 있습니다. 다음 연습에서는 텍스트 템플릿 디버그를 수행할 수 있는 작업의 일부를 보여 줍니다.  
  
> [!NOTE]
> 텍스트에 대 한 자세한 내용은 템플릿 일반적으로 참조 [코드 생성 및 T4 텍스트 템플릿](../modeling/code-generation-and-t4-text-templates.md)합니다. 텍스트 템플릿 디버깅 하는 방법에 대 한 자세한 내용은 참조 하세요. [연습: 텍스트 템플릿 디버그](https://msdn.microsoft.com/library/5c3fd3b7-c110-4e86-a22f-d5756be6b94f)합니다.  
  
## <a name="creating-a-domain-specific-language-solution"></a>도메인별 언어 솔루션 만들기  
 이 절차에서는 다음과 같은 특징이 있는 도메인별 언어 솔루션을 만들 수 있습니다.  
  
- 이름: DebuggingTestLanguage  
  
- 솔루션 템플릿: 최소 언어  
  
- 파일 확장명:.ddd  
  
- 회사 이름: Fabrikam  
  
  도메인별 언어 솔루션을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [방법: 도메인 특정 언어 솔루션 만들기](../modeling/how-to-create-a-domain-specific-language-solution.md)를 참조하세요.  
  
## <a name="creating-a-text-template"></a>텍스트 템플릿 만들기  
 텍스트 템플릿은 솔루션에 추가 합니다.  
  
#### <a name="to-create-a-text-template"></a>텍스트 템플릿을 만들려면  
  
1. 솔루션을 빌드하고 디버거에서 실행을 시작 합니다. (에 **빌드** 메뉴에서 클릭 **솔루션 다시 빌드**를 한 후는 **디버그** 메뉴를 클릭 **디버깅 시작**.) Visual Studio의 새 인스턴스를 디버깅 프로젝트를 엽니다.  
  
2. 라는 텍스트 파일을 추가 `DebugTest.tt` 디버깅 프로젝트에 있습니다.  
  
3. 있는지 확인 합니다 **사용자 지정 도구** DebugTest.tt의 속성이 `TextTemplatingFileGenerator`합니다.  
  
## <a name="debugging-directives-that-access-a-model-from-a-text-template"></a>텍스트 템플릿에서 모델에 액세스 하는 디버깅 지시문  
 문 및 식 텍스트 템플릿에서 모델에 액세스 하기 전에 생성된 된 지시문 프로세서를 먼저 호출 해야 합니다. 생성 된 지시문 프로세서를 호출 클래스 모델에 사용할 수 있도록 텍스트 템플릿 코드를 속성으로. 자세한 내용은 [텍스트 템플릿에서 모델에 액세스](../modeling/accessing-models-from-text-templates.md)합니다.  
  
 다음 절차에서는 잘못 된 속성 이름과 잘못 된 지시문 이름을 디버깅 합니다.  
  
#### <a name="to-debug-an-incorrect-directive-name"></a>잘못 된 지시문 이름을 디버깅 하려면  
  
1. DebugTest.tt의 코드를 다음 코드로 바꿉니다.  
  
    > [!NOTE]
    > 코드는 오류를 포함합니다. 디버깅을 위해 오류를 소개 하기.  
  
    ```csharp  
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
  
    Model: <#= this.ExampleModel #>  
    <#  
    foreach (ExampleElement element in this.ExampleModel.Elements)   
    {   
    #>   
        Element: <#= element.Name #>  
    <#   
    }  
    #>  
    ```  
  
    ```vb  
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ modelRoot processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
  
    Model: <#= Me.ExampleModel #>  
    <#  
    For Each element as ExampleElement in Me.ExampleModel.Elements  
    #>   
        Element: <#= element.Name #>  
    <#   
    Next  
    #>  
    ```  
  
2. **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     합니다 **오류 목록** 창에이 오류가 표시 됩니다.  
  
     **'DebuggingTestLanguageDirectiveProcessor' 프로세서에서 'modelRoot' 지시문을 지원 하지 않습니다. 변환 실행 되지 않습니다.**  
  
     이 경우 지시문 호출에 잘못 된 지시문 이름을 포함합니다. 사용자가 지정한 `modelRoot` 지시문 이름을 하지만 올바른 지시문 이름을 그대로 `DebuggingTestLanguage`합니다.  
  
3. 오류를 두 번 클릭 합니다 **오류 목록** 창의 코드를 이동할 수 있습니다.  
  
4. 코드를 수정 하려면 지시문 이름을 변경 `DebuggingTestLanguage`합니다.  
  
     변경 내용은 강조 표시 됩니다.  
  
    ```csharp  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
    ```  
  
    ```vb  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=ExampleModel" #>  
    ```  
  
5. **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     이제 시스템 텍스트 템플릿을 변환 하 고 해당 출력 파일을 생성 합니다. 에 오류가 표시 되지 것입니다 합니다 **오류 목록** 창입니다.  
  
#### <a name="to-debug-an-incorrect-property-name"></a>올바르지 않은 속성 이름을 디버깅 하려면  
  
1. DebugTest.tt의 코드를 다음 코드로 바꿉니다.  
  
    > [!NOTE]
    > 코드는 오류를 포함합니다. 디버깅을 위해 오류를 소개 하기.  
  
    ```csharp  
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= this.ExampleModel #>  
    <#  
    foreach (ExampleElement element in this.ExampleModel.Elements)   
    {   
    #>   
        Element: <#= element.Name #>  
    <#   
    }  
    #>  
    ```  
  
    ```vb  
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= Me.ExampleModel #>  
    <#  
    For Each element as ExampleElement in Me.ExampleModel.Elements  
    #>   
        Element: <#= element.Name #>  
    <#   
    Next  
    #>  
    ```  
  
2. 에 **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     합니다 **오류 목록** 창이 나타나고 이러한 오류 중 하나가 표시 됩니다.  
  
     (C#)  
  
     **변환을 컴파일하는 중: Microsoft.VisualStudio.TextTemplating\<GUID>. GeneratedTextTransformation' 'ExampleModel'에 대 한 정의 없습니다**  
  
     (Visual Basic)  
  
     **변환을 컴파일하는 중: 'ExampleModel'의 구성원이 아닙니다. ' Microsoft.VisualStudio.TextTemplating\<GUID >. GeneratedTextTransformation'.**  
  
     이 경우에 텍스트 템플릿 코드가 올바르지 않은 속성 이름을 포함합니다. 사용자가 지정한 `ExampleModel` 속성 이름을 하지만 올바른 속성 이름은 `LibraryModel`합니다. 올바른 속성 이름을 찾을 수 있습니다는 다음 코드에 표시 된 대로 매개 변수를 제공 합니다.  
  
    ```  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
    ```  
  
3. 코드를 이동할 오류 목록 창에서 오류를 두 번 클릭 합니다.  
  
4. 코드를 수정 하려면 속성 이름을 변경 `LibraryModel` 텍스트 템플릿 코드에서.  
  
     변경 내용은 강조 표시되어 있습니다.  
  
    ```csharp  
    <#@ template language="C#" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= this.LibraryModel #>  
    <#  
    foreach (ExampleElement element in this.LibraryModel.Elements)   
    {   
    #>   
        Element: <#= element.Name #>  
    <#   
    }  
    #>  
    ```  
  
    ```vb  
    <#@ template language="VB" inherits="Microsoft.VisualStudio.TextTemplating.VSHost.ModelingTextTransformation"#>  
    <#@ output extension=".txt" #>  
    <#@ DebuggingTestLanguage processor="DebuggingTestLanguageDirectiveProcessor" requires="fileName='Sample.ddd'" provides="ExampleModel=LibraryModel" #>  
  
    Model: <#= Me.LibraryModel #>  
    <#  
    For Each element as ExampleElement in Me.LibraryModel.Elements  
    #>   
        Element: <#= element.Name #>  
    <#   
    Next  
    #>  
    ```  
  
5. **솔루션 탐색기**DebugTest.tt를 마우스 오른쪽 단추로 클릭 한 다음 클릭 **사용자 지정 도구 실행**합니다.  
  
     이제 시스템 텍스트 템플릿을 변환 하 고 해당 출력 파일을 생성 합니다. 에 오류가 표시 되지 것입니다 합니다 **오류 목록** 창입니다.

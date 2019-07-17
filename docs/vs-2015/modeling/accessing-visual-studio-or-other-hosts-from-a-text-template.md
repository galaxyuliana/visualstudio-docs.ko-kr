---
title: 텍스트 템플릿에서 Visual Studio 2015 또는 다른 호스트 액세스 | Microsoft Docs
titleSuffix: ''
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: a68886da-7416-4785-8145-3796bb382cba
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d26c168780051d3644d04d209001bf0cc9a551cb
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179080"
---
# <a name="accessing-visual-studio-or-other-hosts-from-a-text-template"></a>텍스트 템플릿에서 Visual Studio 또는 다른 호스트 액세스
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

텍스트 템플릿에서 같은 템플릿을 실행 하는 호스트에 의해 노출 되는 속성과 메서드를 사용할 수 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]입니다.

 이 일반 텍스트 템플릿, 없습니다 전처리 된 텍스트 템플릿 적용 됩니다.

## <a name="obtaining-access-to-the-host"></a>호스트에 대 한 액세스를 얻기
 설정할 `hostspecific="true"` 에 `template` 지시문입니다. 이렇게 하면 사용할 수 있습니다 `this.Host`, 형식이 있는 <xref:Microsoft.VisualStudio.TextTemplating.ITextTemplatingEngineHost>합니다. 이 형식에 멤버가 사용할 수 있는, 예를 들어 파일 이름을 확인 하 고 오류를 기록 합니다.

### <a name="resolving-file-names"></a>파일 이름이 확인
 텍스트 템플릿 기준으로 한 파일의 전체 경로 찾으려면이 사용 합니다. Host.ResolvePath() 합니다.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.IO" #>
<#
 // Find a path within the same project as the text template:
 string myFile = File.ReadAllText(this.Host.ResolvePath("MyFile.txt"));
#>
Content of myFile is:
<#= myFile #>

```

### <a name="displaying-error-messages"></a>오류 메시지를 표시합니다.
 이 예제에서는 서식 파일을 변환 하는 경우 메시지를 기록 합니다. 호스트에 있으면 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]를 오류 창에 추가 됩니다.

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ import namespace="System.CodeDom.Compiler" #>
<#
  string message = "test message";
  this.Host.LogErrors(new CompilerErrorCollection()
    { new CompilerError(
       this.Host.TemplateFile, // Identify the source of the error.
       0, 0, "0",   // Line, column, error ID.
       message) }); // Message displayed in error window.
#>

```

## <a name="using-the-visual-studio-api"></a>Visual Studio API를 사용 하 여
 텍스트 템플릿을 실행 하는 경우 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]를 사용할 수 있습니다 `this.Host` 제공한 서비스에 액세스 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 및 패키지 또는 로드 되는 확장 합니다.

 설정 hostspecific = "true" 및 캐스팅 `this.Host` 에 <xref:System.IServiceProvider>입니다.

 이 예제는 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] API <xref:EnvDTE.DTE>, 서비스로:

```csharp
<#@ template hostspecific="true" language="C#" #>
<#@ output extension=".txt" #>
<#@ assembly name="EnvDTE" #>
<#@ import namespace="EnvDTE" #>
<#
 IServiceProvider serviceProvider = (IServiceProvider)this.Host;
 DTE dte = serviceProvider.GetService(typeof(DTE)) as DTE;
#>
Number of projects in this solution: <#=  dte.Solution.Projects.Count #>

```

## <a name="using-hostspecific-with-template-inheritance"></a>HostSpecific 템플릿 상속 사용
 지정할 `hostspecific="trueFromBase"` 사용 하는 경우는 `inherits` 특성을 지정 하는 서식 파일에서 상속 하는 경우 및 `hostspecific="true"`합니다. 이 컴파일러 경고 결과를 방지 하는 속성 `Host` 두 번 선언 되었습니다.

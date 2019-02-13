---
title: UidManager 작업 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
dev_langs:
- VB
- CSharp
- C++
- jsharp
helpviewer_keywords:
- UidManager task [WPF MSBuild]
- UidManager task [WPF MSBuild], parameters
- managing UIDs when localizing XAML elements [WPF MSBuild]
- localizing XAML elements [WPF MSBuild], managing UIDs
- checking UIDs when localizing XAML elements [WPF MSBuild]
ms.assetid: 4fc7b5a5-11b0-46ca-9656-8c2a0b08d1fe
caps.latest.revision: 8
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 4d88841bae804cc68f7557cbed4413b8f754d4b4
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54796645"
---
# <a name="uidmanager-task"></a>UidManager 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

  
<xref:Microsoft.Build.Tasks.Windows.UidManager> 작업은 소스 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 파일에 포함된 모든 [!INCLUDE[TLA#tla_xaml](../includes/tlasharptla-xaml-md.md)] 요소를 지역화하기 위해 UID(고유 식별자)를 확인, 업데이트 또는 제거합니다.  
  
## <a name="task-parameters"></a>작업 매개 변수  
  
|매개 변수|설명|  
|---------------|-----------------|  
|`IntermediateDirectory`|선택적 **문자열** 매개 변수입니다.<br /><br /> **MarkupFiles** 매개 변수로 지정된 소스 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 파일을 백업하는 데 사용되는 디렉터리를 지정합니다.|  
|`MarkupFiles`|필수 **ITaskItem[]** 매개 변수입니다.<br /><br /> UID 확인, 업데이트 또는 제거를 포함할 소스 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 파일을 지정합니다.|  
|`Task`|필수 **String** 매개 변수입니다.<br /><br /> 수행하려는 UID 관리 작업을 지정합니다. 유효한 옵션은 **Check**, **Update** 또는 **Remove**입니다.|  
  
## <a name="example"></a>예  
 다음 예제에서는 <xref:Microsoft.Build.Tasks.Windows.UidManager> 작업을 사용하여 지정된 소스 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 파일에 해당 UID를 갖는 [!INCLUDE[TLA2#tla_xaml](../includes/tla2sharptla-xaml-md.md)] 요소가 포함되어 있는지를 확인합니다.  
  
```  
<Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <UsingTask   
    TaskName="Microsoft.Build.Tasks.Windows.UidManager"   
    AssemblyFile="C:\Program Files\Reference Assemblies\Microsoft\Framework\v3.0\PresentationBuildTasks.dll" />  
  <Target Name="UidManagerTask">  
    <UidManager  
      Task="Check"  
      MarkupFiles="Page1.xaml;Page2.xaml"  
      IntermediateDirectory="c:\UidManagerIntermediateDirectory" />  
  </Target>  
</Project>  
```  
  
## <a name="see-also"></a>참고 항목  
 [WPF MSBuild 참조](../msbuild/wpf-msbuild-reference.md)   
 [작업 참조](../msbuild/wpf-msbuild-task-reference.md)   
 [MSBuild 참조](../msbuild/msbuild-reference.md)   
 [작업 참조](../msbuild/msbuild-task-reference.md)   
 [WPF 애플리케이션 빌드(WPF)](http://msdn.microsoft.com/library/a58696fd-bdad-4b55-9759-136dfdf8b91c)   
 [방법: 애플리케이션 지역화](http://msdn.microsoft.com/library/5001227e-9326-48a4-9dcd-ba1b89ee6653)

---
title: RC 작업 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: msbuild
ms.topic: reference
f1_keywords:
- VC.Project.VCResourceCompilerTool.UndefineProcessorDefinitions
- vc.task.rc
- VC.Project.VCResourceCompilerTool.SuppressStartupBanner
- VC.Project.VCResourceCompilerTool.NullTerminateStrings
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- RC task (MSBuild (Visual C++))
- MSBuild (Visual C++), RC task
ms.assetid: 2fd26c75-a056-4dda-9f7e-2f90d3748d88
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 9bc8b770e654442f14e693fda35d7cf6f5edbd12
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158263"
---
# <a name="rc-task"></a>RC 작업
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Microsoft Windows 리소스 컴파일러 도구, rc.exe를 래핑합니다. **RC** 작업은 커서, 아이콘, 비트맵, 대화 상자 및 글꼴과 같은 리소스를 리소스(.res) 파일로 컴파일합니다. 자세한 내용은 [MSDN](http://go.microsoft.com/fwlink/?LinkId=737) 웹 사이트에서 "리소스 컴파일러"를 참조하세요.  
  
## <a name="parameters"></a>매개 변수  
 다음 표에서는 RCtask의 매개 변수에 대해 설명합니다. 대부분의 작업 매개 변수 및 몇 가지 매개 변수 집합은 명령줄 옵션에 해당합니다.  
  
|매개 변수|설명|  
|---------------|-----------------|  
|**AdditionalIncludeDirectories**|선택적 **String[]** 매개 변수입니다.<br /><br /> 포함 파일을 검색할 디렉터리 목록에 디렉터리를 추가합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/I** 옵션을 참조하세요.|  
|**AdditionalOptions**|선택적 **문자열** 매개 변수입니다.<br /><br /> 명령줄 optionsor 예제 목록은 **"** _/option1 /option2 /option#_ "입니다. 이 매개 변수를 사용하여 다른 **RC** 작업 매개 변수로 표현되지 않는 명령줄 옵션을 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 옵션을 참조하세요.|  
|**문화권**.|선택적 **문자열** 매개 변수입니다.<br /><br /> 리소스에서 사용되는 문화권을 나타내는 로캘 ID를 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/l** 옵션을 참조하세요.|  
|**IgnoreStandardIncludePath**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 리소스 컴파일러가 헤더 파일이나 리소스 파일을 검색할 때 INCLUDE 환경 변수를 검사하는 것을 금지합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/x** 옵션을 참조하세요.|  
|**NullTerminateStrings**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 문자열 테이블의 모든 문자열을 null로 끝냅니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/n** 옵션을 참조하세요.|  
|**PreprocessorDefinitions**|선택적 **String[]** 매개 변수입니다.<br /><br /> 리소스 컴파일러에 대한 하나 이상의 전처리기 기호를 정의합니다. 매크로 기호 목록을 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/d** 옵션을 참조하세요. 이 표의 **UndefinePreprocessorDefinitions**도 참조하세요.|  
|**ResourceOutputFileName**|선택적 **문자열** 매개 변수입니다.<br /><br /> 리소스 파일 이름을 지정합니다. 리소스 파일 이름을 지정합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/fo** 옵션을 참조하세요.|  
|**ShowProgress**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 컴파일러의 진행 상황을 보고하는 메시지가 표시됩니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/v** 옵션을 참조하세요.|  
|**소스**|필수 `ITaskItem[]` 매개 변수입니다.<br /><br /> 작업에서 사용하고 내보낼 수 있는 MSBuild 소스 파일 항목의 배열을 정의합니다.|  
|**SuppressStartupBanner**|선택적 **Boolean** 매개 변수입니다.<br /><br /> `true`인 경우 작업을 시작할 때 저작권과 버전 번호 메시지가 표시되지 않도록 합니다.<br /><br /> 자세한 내용은 **/?** 명령줄 옵션을 입력하고 **/nologo** 옵션을 참조하세요.|  
|**TrackerLogDirectory**|선택적 **문자열** 매개 변수입니다.<br /><br /> 추적기 로그 디렉터리를 지정합니다.|  
|**UndefinePreprocessorDefinitions**|전처리기 기호의 정의를 해제합니다.<br /><br /> 자세한 내용은 MSDN 웹 사이트의 [RC 사용(RC 명령줄)](http://go.microsoft.com/fwlink/?LinkId=155730)에서 **/u** 옵션을 참조하세요. 이 표의 **PreprocessorDefinitions**도 참조하세요.|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [작업 참조](../msbuild/msbuild-task-reference.md)

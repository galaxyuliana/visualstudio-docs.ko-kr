---
title: '방법: 표준 코드 분석 체크 인 정책 만들기 또는 업데이트 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.policyeditor
helpviewer_keywords:
- code analysis, migrating check-in policy
ms.assetid: 458eb3b8-bb5e-4056-82b7-7079ce9c4089
caps.latest.revision: 31
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 47e7c2b6e02aab3b6b1df0c54ba91668bbb2673c
ms.sourcegitcommit: 75807551ea14c5a37aa07dd93a170b02fc67bc8c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/11/2019
ms.locfileid: "67825807"
---
# <a name="how-to-create-or-update-standard-code-analysis-check-in-policies"></a>방법: 표준 코드 분석 체크 인 정책 만들기 또는 업데이트
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

코드 분석 체크 인 정책을 사용 하 여 팀 프로젝트의 모든 코드 프로젝트에 대해 코드 분석 실행 수 있도록 요구할 수 있습니다. 코드 분석에 필요한 코드 베이스에 체크 인 된 코드의 품질을 향상 시킬 수 있습니다.  
  
> [!NOTE]
> 이 기능은 Team Foundation Server를 사용 하는 경우에 사용할 수 있습니다.  
  
 코드 분석 체크 인 정책 팀 프로젝트 설정에서 설정 되 고 팀 프로젝트의 각 코드 프로젝트에 적용 합니다. 코드 분석 실행 코드 프로젝트에 대 한 프로젝트 (.xxproj) 파일에서 코드 프로젝트에 대해 구성 됩니다. 코드 분석 실행은 로컬 컴퓨터에서 수행 됩니다. 팀 프로젝트 설정의 규칙은 컴퓨터에서 수행 해야 코드 분석 체크 인 정책을 사용 하면, 체크 인 된 코드 프로젝트의 파일은 마지막 편집 후 컴파일해야 및 최소한의 코드 분석 실행을 포함 하는 경우 여기서 c hanges가 이루어졌습니다.  
  
- 관리 되는 코드를 지정 하 여 체크 인 정책 설정 된 *규칙 집합* 코드 분석 규칙의 하위 집합을 포함 하는 합니다.  
  
- C /C++ 코드를 체크 인 정책에 따라 모든 코드 분석 규칙이 실행 됩니다. 팀 프로젝트의 개별 코드 프로젝트에 대 한 특정 규칙을 사용 하지 않도록 설정 하는 전처리기 지시문을 추가할 수 있습니다.  
  
  관리 코드에 대 한 체크 인 정책을 지정한 후 팀 멤버는 팀 프로젝트 정책 설정이 코드 프로젝트에 대 한 코드 분석 설정을 동기화 할 수 있습니다.  
  
### <a name="to-open-the-check-in-policy-editor"></a>체크 인 정책 편집기를 열려면  
  
1. 팀 탐색기에서 팀 프로젝트 이름을 마우스 오른쪽 **팀 프로젝트 설정**를 클릭 하 고 **소스 제어**입니다.  
  
2. 에 **소스 제어** 대화 상자를 선택 합니다 **체크 인 정책** 탭.  
  
3. 다음 작업 중 하나를 수행합니다.  
  
    - 클릭 **추가** 새 체크 인 정책을 만들어야 합니다.  
  
    - 기존 두 번 클릭 **코드 분석** 항목에 **정책 유형** 정책을 변경 하려면 목록입니다.  
  
### <a name="to-set-policy-options"></a>정책 옵션을 설정 하려면  
  
- 선택 하거나 다음 옵션을 선택 취소 합니다.  
  
    |옵션|Description|  
    |------------|-----------------|  
    |**체크 인 현재 솔루션의 일부인 파일만 포함 하도록 적용 합니다.**|코드 분석 솔루션 및 프로젝트 구성 파일에 지정 된 파일 에서만 실행할 수 있습니다. 이 정책은 솔루션의 일부인 모든 코드를 분석 하는 것을 보장 합니다.|  
    |**C 적용 /C++ 코드 분석 (/analyze)**|모든 C 또는 C++ 프로젝트를 빌드하는 /analyze 컴파일러 옵션 검사 하기 전에 코드 분석을 실행 하려면.|  
    |**관리 코드에 대 한 코드 분석 적용**|모든 관리 되는 프로젝트 코드 분석 실행 검사 하기 전에 작성 해야 합니다.|  
  
- 
  
### <a name="to-specify-a-managed-rule-set"></a>관리 되는 규칙 집합을 지정 하려면  
  
- **이 규칙 집합 실행** 목록에서 다음 방법 중 하나를 사용 합니다.  
  
  - Microsoft 표준 규칙 집합을 선택 합니다.  

  - 사용자 지정 규칙 집합을 선택 하려면 클릭  **\<...에 소스 제어에서 규칙 집합 선택 >** , 소스 제어 브라우저에서 규칙 집합의 버전 제어 경로 입력 합니다. 버전 제어 경로 구문은 다음과 같습니다.  

  - **$/** `TeamProjectName` **/** `VersionControlPath`  

  - 설정 만들기 및 사용자 지정 체크 인 정책 규칙을 구현 하는 방법에 대 한 자세한 내용은 [관리 코드에 대 한 사용자 지정 구현 체크 인 정책을](../code-quality/implementing-custom-code-analysis-check-in-policies-for-managed-code.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [코드 분석 체크 인 정책 만들기 및 사용](../code-quality/creating-and-using-code-analysis-check-in-policies.md)

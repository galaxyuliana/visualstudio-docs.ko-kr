---
title: 코드 분석 도구를 사용 하 여 응용 프로그램 품질 분석 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.analysisresults
helpviewer_keywords:
- application quality, analyzing
- code analysis
- team-based development, analyzing application quality
ms.assetid: 21680516-ddb5-446d-90d4-19d94f6ec699
caps.latest.revision: 26
author: gewarren
ms.author: gewarren
manager: wpickett
ms.openlocfilehash: 83fbe8b372d021e0cec4faccfd0b22fcaa8af30d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68157097"
---
# <a name="analyzing-application-quality-by-using-code-analysis-tools"></a>코드 분석 도구를 사용하여 애플리케이션 품질 분석
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

섹션 내용  
 [관리 코드 품질 분석](../code-quality/analyzing-managed-code-quality-by-using-code-analysis.md)  
 관리 코드에 대한 Visual Studio Code 분석에서는 Microsoft .NET Framework 디자인 지침에 명시된 프로그래밍 및 디자인 규칙의 위반과 같은 관리되는 어셈블리 관련 정보를 제공합니다. 경고 메시지는 관련 프로그래밍 및 디자인 문제를 식별하며 가능한 경우 문제 해결 방법에 대한 정보를 제공합니다.  
  
 [코드 분석을 사용하여 C/C++ 코드 품질 분석](../code-quality/analyzing-c-cpp-code-quality-by-using-code-analysis.md)  
 C/C++ 코드 분석 도구는 C/C++ 소스 코드에서 발생할 수 있는 오류에 대한 정보를 개발자에게 제공합니다. 이 도구를 통해 보고되는 일반적인 코딩 오류에는 버퍼 오버런, 초기화되지 않은 메모리, null 포인터 역참조, 메모리 및 리소스 누수 등이 포함됩니다.  
  
 [규칙 집합을 사용하여 코드 분석 규칙 그룹화](../code-quality/using-rule-sets-to-group-code-analysis-rules.md)  
 선택 및 작성할 *규칙 집합* 프로젝트에 적용 합니다.  
  
 [코드 분석 애플리케이션 오류](../code-quality/code-analysis-application-errors.md)  
 코드 분석 기능에서 오류를 수정합니다.  
  
 [팀 프로젝트 체크 인 정책을 사용하여 코드 품질 향상](../code-quality/enhancing-code-quality-with-team-project-check-in-policies.md)  
 TFVC(Team Foundation Version Control)를 사용할 때는 팀 프로젝트에 대한 체크 인 정책을 만들어 코드 품질을 향상시키고 그룹 개발을 보다 효율적으로 수행할 수 있게 해주는 방법을 적용할 수 있습니다. 체크 인 정책은 팀 프로젝트 수준에서 설정되어 코드 체크 인이 허용되기 전에 개발자 컴퓨터에서 적용되는 규칙입니다.  
  
### <a name="code-analysis-for-drivers"></a>드라이버에 대한 코드 분석  
 코드 분석 도구는 드라이버 소스 코드를 체계적으로 분석하여 안정성과 드라이버의 신뢰성을 향상시킬 수 있습니다.  
  
 [코드 분석 도구를 사용 하 여 드라이버 품질 분석](/windows-hardware/drivers/devtest/tools-for-verifying-drivers)  
 드라이버용 코드 분석은 C에서 기본 코딩 오류를 감지 하는 컴파일 시간 정적 확인 도구 및 C++ 프로그램 및 (주로) 커널 모드 드라이버 코드에서 오류를 감지 하도록 설계 된 특수 한 모듈을 포함 합니다. SDV(정적 드라이버 확인 프로그램)는 Windows 커널 모드 드라이버의 소스 코드를 체계적으로 분석하는 정적 검증 도구입니다. SDV는 드라이버가 Windows 운영 체제 커널과 제대로 상호 작용하는지 여부를 결정합니다.  
  
 [드라이버 경고에 대한 코드 분석](http://go.microsoft.com/fwlink/?LinkId=225920)  
 드라이버에 대한 코드 분석이 드라이버 코드에서 가능한 오류를 검색할 때 보고하는 경고에 대해 설명합니다.  
  
## <a name="related-tasks"></a>관련 작업  
 [관리 코드의 복잡성 및 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)  
 여기에 설명을 삽입합니다.  
  
 [코드 단위 테스트](../test/unit-test-your-code.md)  
 여기에 설명을 삽입합니다.

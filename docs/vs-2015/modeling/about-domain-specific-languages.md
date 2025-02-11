---
title: 도메인 특정 언어에 대 한 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language
ms.assetid: 29e5b6f2-ece4-4f3b-ab08-5f957418702f
caps.latest.revision: 28
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 0ddfc51c54c04ad0d79d7ef180a027cbd253ac09
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68165432"
---
# <a name="about-domain-specific-languages"></a>도메인별 언어 정보
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

C# 등 UML 범용 언어에서 달리 도메인 특정 언어 (DSL)는 문 특정 문제 영역에 도메인 익스프레스 하도록 설계 되었습니다.  
  
 잘 알려진 Dsl 정규식과 SQL을 포함 합니다. 각 DSL은 자체 범위를 벗어나는 아이디어를 설명 하는 텍스트 문자열 또는 데이터베이스에 있지만 훨씬 더 작업을 설명 하는 범용 언어 보다 훨씬 더 바람직합니다. 개별 산업 자신의 Dsl 수도 있습니다. 예를 들어 통신 업계에서 호출 설명 언어는 광범위 하 게 전화를 걸의 상태 순서를 지정 하 고 공중에서 업계를 이동 하는 데 사용 됩니다 표준 DSL는 항공편 예약에 설명 하는 데 사용 됩니다.  
  
 비즈니스 및 프로젝트가 DSL을 사용 하 여 기술 할 수 있는 개념의 특별 한 집합을 사용 하 여 처리 합니다. 예를 들어, 이러한 응용 프로그램 중 하나에 대 한 DSL을 정의할 수 있습니다.  
  
- 웹 사이트의 탐색 경로 계획입니다.  
  
- 전자 부품에 대 한 다이어그램을 연결 합니다.  
  
- 컨베이어 벨트 및 수하물 처리 장비 공항에 대 한 네트워크입니다.  
  
  DSL을 디자인할 때 정의 된 *도메인 클래스* 각 도메인에 웹 페이지, lamp, 또는 공항 체크인 데스크와 같은 중요 한 개념에 대 한 합니다. 정의한 *도메인 관계* 개념을 함께 연결할 컨베이어 벨트, 하이퍼링크 및 통신 등입니다.  
  
  DSL의 사용자가 만들거나 *모델입니다.* 모델은 *인스턴스* DSL의 합니다. 예를 들어 특정 웹 사이트에 또는 특정 장치 또는 처리 시스템의 특정 공항 수하물 연결은 설명 합니다.  
  
  사용자가 다이어그램 또는 Windows form으로 모델을 볼 수 있습니다. 모델도 볼 수 있습니다 XML로 저장 되는 방식을 인. DSL을 정의 하는 경우 각 도메인 클래스 및 관계의 인스턴스는 사용자의 화면에 표시 되는 방식을 정의할 수 있습니다. 일반적인 DSL 아이콘 또는 사각형 화살표로 연결 된 컬렉션으로 표시 됩니다.  
  
  다음 그림에는 다이어그램 DSL에서 작은 모델을 보여 줍니다.  
  
  ![Tudor 패밀리 트리 모델](../modeling/media/tudor-familytreemodel.png "Tudor_FamilyTreeModel")  
  
## <a name="what-you-can-do-with-dsls"></a>Dsl을 사용 하 여 수행할 수 있는 작업  
 DSL의 일반적인 응용 프로그램 코드 또는 기타 아티팩트를 생성 하는 것입니다. DSL을 정의 하는 경우 정의할 수 있습니다 *텍스트 템플릿* DSL의 모델을 읽은 하 고 텍스트 파일을 생성 합니다.  
  
 예를 들어, 공항 계획을 가져와 수하물 처리, 일부 계획을 설명 하는 사용자 문서 뿐만 아니라 소프트웨어의 일부를 생성 하는 템플릿을 작성할 수 있습니다.  
  
 DSL을 정의한 경우에 자신의 컴퓨터에 설치할 수 있는 다른 사용자에 게 배포할 수 있습니다. DSL의 사용자가 작성 하 고 모델을 편집 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]합니다.  
  
 메뉴 명령을 정의할 수도 있습니다 및 사용자를 지 원하는 다른 도구에 도움이 되는 DSL은 올바로 사용 하는 새 인스턴스를 만들 수 있도록 하는 항목 템플릿 유효성 검사 제약 조건을 DSL을 편집 합니다. 해당 도구 및 기타를 사용 하 여 하나 이상의 Dsl을 래핑할 수 있습니다 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 통합된 패키지를 확장 합니다.  
  
 일반적으로 도메인 특정 언어 개발 팀에서 여러 제품에 대 한 유사한 코드를 작성 해야 하는 경우 생성 됩니다. 예를 들어 수하물 처리 시스템을 전문적으로 하는 회사는 각 설치에 대 한 코드의 일부를 생성할 수 있습니다 수하물 추적 DSL을 정의 될 수 있습니다. DSL의 이점은에서 생성 된 코드를 신뢰할 수 있는 고객의 요구 사항을 변경 하는 경우 시스템이 신속 하 게 업데이트할 수 있습니다 및 고객에 게에서 이해할 수 있습니다.  
  
 [!INCLUDE[dsl](../includes/dsl-md.md)] 고유한 그래픽 디자이너 및 고유한 다이어그램 표기법을 포함 하는 도메인 특정 언어를 만들고 다음 언어를 사용 하 여 각 프로젝트에 대 한 적절 한 소스 코드를 생성할 수 있습니다.  
  
## <a name="domain-specific-development"></a>도메인 특정 개발  
 도메인 특정 개발은 도메인 특정 언어를 사용 하 고 다음 언어를 생성 하 고 응용 프로그램 개발자에 게 배포 하 여 모델링할 수 있는 응용 프로그램 부분을 식별 하는 프로세스입니다. 응용 프로그램에 관련 된 모델을 생성, 모델을 사용 하 여 소스 코드를 생성 및 다음 소스 코드를 사용 하 여 응용 프로그램을 개발할 도메인 특정 언어를 사용 하는 개발자.  
  
## <a name="aspects-of-graphical-domain-specific-development"></a>그래픽 도메인별 개발 측면  
 그래픽 도메인 특정 언어는 다음과 같은 기능을 포함 해야 합니다.  
  
- Notation  
  
- 도메인 모델  
  
- 아티팩트 생성  
  
- Serialization  
  
- Visual Studio와의 통합  
  
### <a name="notation"></a>Notation  
 도메인 특정 언어를 적당히 작게 쉽게 정의 하 고 나타내는 도메인별 구문을 확장 하는 요소 집합이 있어야 합니다. 표기법 요소를 나타내는 모양 및 연결선 그래픽 다이어그램 화면에서 요소 간의 관계를 나타내는 구성 됩니다. [!INCLUDE[dsl](../includes/dsl-md.md)], 셰이프를 확장 하 고 도메인 특정 언어의 요소를 나타내기 위해 구체화 수 있습니다.  
  
### <a name="domain-model"></a>도메인 모델  
 도메인 특정 언어 요소와 일관 된 문법에 이들 간의 관계의 집합을 결합 해야 합니다. 또한 요소 및 관계의 조합을 유효한 지 여부를 정의 해야 합니다. 예를 들어, 프로그래밍 언어는 일반적으로는 하나의 클래스는 두 번째 클래스에서 파생 되며 두 번째 클래스는 첫 번째 클래스에서 파생 된 순환 상속을 방지 합니다. 명으로 종속 될 수 없습니다 예를 들어, 제약 조건 비즈니스 논리를 표현 하도 사용할 수 있습니다. [!INCLUDE[dsl](../includes/dsl-md.md)] 제약 조건 도메인 특정 언어 가장 필요로 하는 제한의 종류를 나타내는 데 사용 합니다.  
  
### <a name="artifact-generation"></a>아티팩트 생성  
 도메인 특정 언어의 주 목적 중 아티팩트, 예를 들어, 소스 코드, XML 파일 또는 일부 기타 유용한 데이터를 생성 하는 것입니다. 일반적으로 모델 변경 아티팩트 변경을 의미합니다. 사용할 수 있습니다 [!INCLUDE[dsl](../includes/dsl-md.md)] 아티팩트를 생성 하 고 모델을 변경한 경우 파일을 다시 생성 합니다.  
  
### <a name="serialization"></a>Serialization  
 도메인 특정 언어를 편집, 저장, 종료 및 수를 다시 로드 하는 몇 가지 형태로 유지 해야 합니다. [!INCLUDE[dsl](../includes/dsl-md.md)] 정의 및 도메인별 언어 직렬화 되거나 유지 하는 방법을 사용자 지정할 수 있는 XML 형식으로 사용 합니다.  
  
### <a name="integration-with-visual-studio"></a>Visual Studio와의 통합  
 때문에 [!INCLUDE[dsl](../includes/dsl-md.md)] 에 호스팅된 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], 여러 확장 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 창과 컨트롤입니다. 또한 메뉴 명령, 도구 상자 항목 및 기타 요소의 사용자 인터페이스 동작을 사용자 지정할 수 있습니다.  
  
 또한 도메인 특정 언어에 대 한 모델 버스 어댑터를 만들 수 있습니다. 이 어댑터 참조 모델 및 모델과 DSL의 인스턴스를 업데이트 하 고 액세스할 수 있는 코드를 작성할 수 있습니다 내의 요소 수 있습니다. 강력한 모델 버스 메커니즘을 사용 하 여 작성할 수 있습니다 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 여러 모델을 사용 하는 확장 합니다. 또한 모델을 사용 하는 독립 실행형 응용 프로그램을 작성할 수 있습니다. 자세한 내용은 [Visual Studio Modelbus를 사용 하 여 모델 통합](../modeling/integrating-models-by-using-visual-studio-modelbus.md)합니다.  
  
## <a name="benefits-of-domain-specific-development"></a>도메인 특정 개발의 이점  
 도메인 특정 언어에는 다음과 같은 이점을 제공할 수 있습니다.  
  
- 문제 공간을 정확 하 게 맞는 구문이 포함 되어 있습니다.  
  
     범용 언어와 달리 도메인 특정 언어 요소 및 관계 문제 영역의 논리를 직접 나타내는으로 구성 됩니다. 예를 들어, 보험 정책 응용 프로그램 정책 및 클레임에 대 한 요소를 포함 해야 합니다. 도메인 특정 언어를 쉽게 디자인 응용 프로그램 및 찾기 및 논리 오류를 수정 합니다.  
  
- 비 개발자 및 전반적인 디자인을 이해 하는 도메인 모르는 사람들이 있습니다.  
  
     그래픽-도메인별 언어를 사용 하 여 개발자가 아닌 응용 프로그램의 디자인을 쉽게 이해할 수 있도록 도메인의 시각적 표현을 만들 수 있습니다.  
  
- 최종 응용 프로그램의 프로토타입을 만드는 쉽게 수 있습니다.  
  
     개발자는 자신의 모델 수를 클라이언트에 표시 되는 프로토타입 응용 프로그램을 만드는 생성 하는 코드를 사용할 수 있습니다.  
  
## <a name="the-process-of-domain-specific-development"></a>도메인 특정 개발 프로세스  
 도메인 특정 언어를 사용 하는 대부분의 소프트웨어 개발 팀을 만들고 해당 모델을 사용 하려면 다음이 단계를 수행 합니다.  
  
- 팀에서 변경 되지 않는 도메인의 변수 부분을 구분 합니다.  
  
- 개발자가 고정 된 부분에 대 한 코드를 작성 하 고 변수 부분에 대 한 확장 지점을 유지 합니다.  
  
- 수석 소프트웨어 개발자 또는 설계자 변수 부분에 대 한 확장 지점과 도메인 고정 부분의 디자인 패턴을 통합 하는 도메인 특정 언어를 만듭니다.  
  
- 수석 소프트웨어 개발자 또는 설계자 도메인 특정 언어 팀을 생성 하는 다양 한 응용 프로그램 개발자에 게 배포 합니다.  
  
- 모든 개발자는 특정 응용 프로그램에 적용 되는 모델을 만듭니다.

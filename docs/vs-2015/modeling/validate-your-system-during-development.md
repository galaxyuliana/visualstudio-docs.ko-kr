---
title: 개발 하는 동안 시스템 유효성 검사 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- layer diagrams
ms.assetid: c9dafb47-7b1d-4c72-9432-d43be3db1799
caps.latest.revision: 39
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 4570b8ed1afdfff2efd36dbc2f80e97cfbceecac
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65698069"
---
# <a name="validate-your-system-during-development"></a>개발하는 동안 시스템 유효성 검사
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio에서는 소프트웨어와 사용자 요구 사항 및 시스템 아키텍처의 일관성을 유지할 수 있습니다.  
  
 이러한 각 기능을 지원하는 Visual Studio의 버전을 확인하려면 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)를 참조하세요.  
  
## <a name="key-tasks"></a>주요 작업  
 다음 작업으로 소프트웨어의 유효성을 검사합니다.  
  
|**작업**|**관련 항목**|  
|---------------|---------------------------|  
|**모델에 일관성이 있는지 확인 합니다.**<br /><br /> 프로젝트가 모델을 사용 및 해석하는 방법에 따라 일부 요소 조합을 거부하는 것이 유용할 수 있습니다. 예를 들어 항상 [!INCLUDE[TLA2#tla_net](../includes/tla2sharptla-net-md.md)] 규격 이름이 포함되도록 UML 클래스를 제한할 수 있습니다. [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] 확장에서 이와 같은 제약 조건을 정의할 수 있습니다.|-   [UML 모델 유효성 검사](../modeling/validate-your-uml-model.md)<br />-   [UML 모델에 대 한 유효성 검사 제약 조건 정의](../modeling/define-validation-constraints-for-uml-models.md)|  
|**소프트웨어가 사용자 요구 사항을 충족하는지 확인합니다**.<br /><br /> 요구 사항 및 아키텍처 모델을 사용하여 시스템 및 해당 구성 요소의 테스트를 구성하도록 지원할 수 있습니다. 이렇게 하면 사용자 및 기타 이해 관계자에게 중요한 요구 사항을 테스트하는지 확인할 수 있고 요구 사항이 변경될 때 테스트를 빠르게 업데이트할 수 있습니다.|-   [모델에서 테스트 개발](../modeling/develop-tests-from-a-model.md)|  
|**소프트웨어와 의도한 시스템 디자인의 일관성이 유지되는지 확인합니다.**<br /><br /> 레이어 다이어그램에서는 애플리케이션 구성 요소 간의 의도한 종속성을 설명합니다. 개발하는 동안 코드의 실제 종속성이 의도한 디자인을 따르는지 확인할 수 있습니다.|-   [코드에서 레이어 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)<br />-   [레이어 다이어그램을 사용 하 여 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)|  
  
## <a name="external-resources"></a>외부 리소스  
  
|**범주**|**링크**|  
|------------------|---------------|  
|**비디오**|![비디오 링크](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: Doug Seven: 코드 이해 및 Visual Studio 2010을 사용 하 여 시스템 디자인](http://go.microsoft.com/fwlink/?LinkId=216100)<br /><br /> ![비디오 링크](../data-tools/media/playvideo.gif "PlayVideo") [Channel 9: 레이어 다이어그램을 사용 하 여 응용 프로그램 설계](http://go.microsoft.com/fwlink/?LinkID=201117)<br /><br /> ![비디오 링크](../data-tools/media/playvideo.gif "PlayVideo") [MSDN 어떻게 할까요? 시리즈: 레이어 다이어그램을 사용 하 여 코드 유효성을 검사 하는 방법](http://go.microsoft.com/fwlink/?LinkID=214405)|  
|**포럼**|-   [Visual Studio 시각화 및 모델링 도구](http://go.microsoft.com/fwlink/?LinkId=184720)<br />-   [Visual Studio 시각화 및 모델링 SDK(DSL 도구)](http://go.microsoft.com/fwlink/?LinkId=184721)|  
|**블로그**|-   [Visual Studio ALM + Team Foundation Server 블로그](http://go.microsoft.com/fwlink/?LinkID=201340)|  
|**기술 문서 및 저널**|[MSDN 아키텍처 센터](http://go.microsoft.com/fwlink/?LinkId=201343)|  
  
## <a name="see-also"></a>참고 항목  
 [응용 프로그램 테스트](https://msdn.microsoft.com/library/796b7d6d-ad45-4772-9719-55eaf5490dac)   
 [UML 모델 및 다이어그램 확장](../modeling/extend-uml-models-and-diagrams.md)   
 [사용자 요구 사항 모델링](../modeling/model-user-requirements.md)   
 [아키텍처 분석 및 모델링](../modeling/analyze-and-model-your-architecture.md)

---
title: 개발하는 동안 시스템 유효성 검사
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9fb9810f1c212dfb881f5725676a79c6307b9cfa
ms.sourcegitcommit: 6a19c5ece38a70731496a38f2ef20676ff18f8a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65476496"
---
# <a name="validate-your-system-during-development"></a>개발하는 동안 시스템 유효성 검사

Visual Studio 소프트웨어와 사용자 요구 사항 및 시스템의 아키텍처를 사용 하 여 일관성을 유지 하는 데 도움이 됩니다.

이러한 각 기능을 지원하는 Visual Studio의 버전을 확인하려면 [Version support for architecture and modeling tools](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)를 참조하세요.

## <a name="key-tasks"></a>주요 작업

소프트웨어의 유효성을 검사 하려면 다음 작업을 사용 합니다.

|**작업**|**관련 항목**|
|-|-|
|**소프트웨어가 사용자 요구 사항을 충족하는지 확인합니다**.<br /><br />시스템 및 해당 구성 요소의 테스트를 구성할 수 있도록 요구 사항 및 아키텍처 모델을 사용 합니다. 이렇게 하면 사용자 및 기타 이해 관계자에게 중요한 요구 사항을 테스트하는지 확인할 수 있고 요구 사항이 변경될 때 테스트를 빠르게 업데이트할 수 있습니다.|- [모델에서 테스트 개발](../modeling/develop-tests-from-a-model.md)|
|**소프트웨어와 의도한 시스템 디자인의 일관성이 유지되는지 확인합니다.**<br /><br />종속성 다이어그램 응용 프로그램의 구성 요소 간의 의도 한 종속성을 설명합니다. 개발하는 동안 코드의 실제 종속성이 의도한 디자인을 따르는지 확인할 수 있습니다.|- [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)<br />- [종속성 다이어그램을 사용 하 여 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)|

## <a name="external-resources"></a>외부 리소스

|**범주**|**링크**|
|-|-|
|**비디오**|![비디오를 연결할](../data-tools/media/playvideo.gif) [Channel 9: Doug Seven: Visual Studio 2010을 사용 하 여 시스템 디자인 및 코드 이해](https://channel9.msdn.com/shows/VS2010Launch/Doug-Seven-Code-Understanding-and-Systems-Design-with-Visual-Studio-2010)<br /><br /> ![비디오를 연결할](../data-tools/media/playvideo.gif) [Channel 9: 응용 프로그램 설계](https://channel9.msdn.com/blogs/clinted/uml-with-vs-2010-part-5-architecting-an-application))|
|**포럼**|- [Visual Studio 시각화 및 모델링 도구](https://social.msdn.microsoft.com/Forums/en-US/home?forum=vsarch)<br />- [Visual Studio 확장성](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx)|

## <a name="see-also"></a>참고자료

- [사용자 요구 사항 모델링](../modeling/model-user-requirements.md)
- [분석 및 모델 아키텍처](../modeling/analyze-and-model-your-architecture.md)

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

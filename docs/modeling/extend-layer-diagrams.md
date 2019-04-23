---
title: 종속성 다이어그램 확장
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, creating extensions
- layer models
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5519328ef69f98737a7744f0162bdc0951433a60
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60082895"
---
# <a name="extend-dependency-diagrams"></a>종속성 다이어그램 확장

만들고 종속성 다이어그램을 업데이트 하 고 Visual Studio에서 종속성 다이어그램에 대해 프로그램 코드의 구조를 확인 하는 코드를 작성할 수 있습니다. 다이어그램의 바로 가기(상황에 맞는) 메뉴에 표시되는 명령을 추가하고, 끌어서 놓기 제스처를 사용자 지정하고, 텍스트 템플릿에서 레이어 모델에 액세스할 수 있습니다. 이러한 확장을 VSIX(Visual Studio Integration Extension)로 패키징하고 다른 Visual Studio 사용자에게 배포할 수 있습니다.

 종속성 다이어그램에 대 한 자세한 내용은 다음을 참조 하세요.

- [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)

- [종속성 다이어그램: 지침](../modeling/layer-diagrams-guidelines.md)

- [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)

- [종속성 다이어그램을 사용하여 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)

## <a name="prereqs"></a> 요구 사항

레이어 확장을 개발하려는 컴퓨터에 다음이 설치되어 있어야 합니다.

- Visual Studio

- [Visual Studio SDK](../extensibility/visual-studio-sdk.md)

- Visual Studio 용 모델링 SDK

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

레이어 확장을 실행하려는 컴퓨터에 적합한 버전의 Visual Studio가 설치되어 있어야 합니다.

종속성 다이어그램을 지 원하는 Visual Studio 버전을 참조 하세요 [아키텍처 및 모델링 도구에 대 한 버전 지원](../modeling/what-s-new-for-design-in-visual-studio.md#VersionSupport)합니다.

## <a name="in-this-section"></a>섹션 내용
 [종속성 다이어그램에 명령 및 제스처 추가](../modeling/add-commands-and-gestures-to-layer-diagrams.md)

 [종속성 다이어그램에 사용자 지정 아키텍처 유효성 검사 추가](../modeling/add-custom-architecture-validation-to-layer-diagrams.md)

 [종속성 다이어그램에 사용자 지정 속성 추가](../modeling/add-custom-properties-to-layer-diagrams.md)

## <a name="see-also"></a>참고 항목

- [종속성 다이어그램: 참조](../modeling/layer-diagrams-reference.md)
- [종속성 다이어그램: 지침](../modeling/layer-diagrams-guidelines.md)
- [코드에서 종속성 다이어그램 만들기](../modeling/create-layer-diagrams-from-your-code.md)
- [종속성 다이어그램을 사용하여 코드 유효성 검사](../modeling/validate-code-with-layer-diagrams.md)

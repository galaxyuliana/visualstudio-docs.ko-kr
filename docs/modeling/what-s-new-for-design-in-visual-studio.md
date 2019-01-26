---
title: 디자인에 대 한 새로운 기능
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- what's new [VIsual Studio ALM], architecture and modeling
- architecture [Visual Studio Ultimate], modeling
- modeling software [Visual Studio ALM], What's New
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8340876527db26354bbef2809aaf26559db617b4
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54948936"
---
# <a name="whats-new-for-design-in-visual-studio"></a>Visual Studio의 디자인에 대한 새로운 기능

## <a name="live-dependency-validation"></a>실시간 종속성 유효성 검사

원치 않는 종속성을 제거 하면 기술적인 문제를 관리 하는 중요 한 부분입니다. 실시간 종속성 유효성 검사를 포함 하는 이제 문제에 대 한 정확한 정보를 제공 되며 오류 목록 및 편집기의 새로운 기능에서 완벽 하 게 애플리케이션을.

![작업의 라이브 종속성 유효성 검사](media/dep-validation-whatsnew-01.png)

제작 환경 확인 종속성 유효성 검사를 더 검색 및 보조 액세스 변경 용어는 "레이어 다이어그램"에서 "종속성 다이어그램"로 변경 되었습니다.

합니다 **아키텍처** 메뉴에는 이제 직접 종속성 다이어그램을 만드는 명령도 포함 됩니다.

![아키텍처 메뉴의 라이브 종속성 항목](media/dep-validation-whatsnew-02.png)

... 및 종속성 다이어그램 및 해당 설명을 보려면에서 계층의 속성 이름을 더 의미 있게 하도록 변경 되었습니다.

![라이브 종속성 속성 이름 업데이트](media/dep-validation-whatsnew-03.png)

이제 표시 솔루션에서 현재 코드에 대 한 분석 결과에 즉시 변경 내용의 영향 다이어그램을 저장할 때마다 됩니다. "종속성 유효성 검사" 명령이 완료 될 때 더 이상까지 필요가 없습니다.

자세한 내용은 참조 하세요. [이 블로그 게시물](https://blogs.msdn.microsoft.com/devops/2016/10/07/live-architecture-dependency-validation-in-visual-studio-15-preview-5/)합니다.

## <a name="uml-designers-have-been-removed"></a>UML 디자이너 제거 되었습니다.

UML 디자이너가이 버전의 Visual Studio Enterprise에서 제거 되었습니다.

* UML 다이어그램 이제 XML 파일로 표시 됩니다.
* UML 모델 탐색기를 더 이상 존재합니다.
* 모델링 프로젝트 참조는 종속성 유효성 검사를 위해 더 이상 사용 됩니다.
* 솔루션 탐색기에서 "레이어 참조" 노드를 더 이상 표시 됩니다.
* 빌드 작업에서 제거 되었습니다-종속성 (레이어) 다이어그램의 "유효성 검사" 빌드 작업을 더 이상 사용
* 버전 간 왕복에 대 한 프로젝트 구조는 유지 관리
* 있습니다 여전히 열기, 만들기, 편집 하 고 수 (계층) 종속성 다이어그램을 XML로 저장
* 디자인 화면에 액세스할 수 없는 (계층) 종속성 다이어그램에 연결 된 TFS 작업 항목
* 더 이상 지원 되지 DSL 또는 계층에서 다시 연결
* Modeling SDK에서 UML 확장은 더 이상 지원

그러나에 대 한 지원은.NET 및 c + + 코드의 아키텍처 시각화를 통해 사용할 수 있습니다 [코드 맵](map-dependencies-across-your-solutions.md), 및 위에서 설명한 종속성 유효성 검사를 향상 합니다.

UML 디자이너의 중요 한 사용자 라면 UML 요구 사항에 맞게 대체 하는 도구를 결정 하는 동안 Visual Studio 2015 또는 이전 버전을 사용 하 여 계속 수 있습니다.

자세한 내용은 참조 하세요. [이 블로그 게시물](https://blogs.msdn.microsoft.com/devops/2016/10/14/uml-designers-have-been-removed-layer-designer-now-supports-live-architectural-analysis/)합니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="a-nameversionsupport-edition-support-for-architecture-and-modeling-tools"></a><a name="VersionSupport" />아키텍처 및 모델링 도구에 대 한 버전 지원

Visual Studio 2017은 여러 버전에서 사용할 수 있습니다. 이러한 일부 아키텍처 및 모델링 도구에 대 한 지원을 제공 합니다. 다음 표에서는 각 도구의 사용 가능 여부를 보여 줍니다.

|**기능**|**Enterprise edition**|**Professional edition**|**Community edition**|
|-|-|-|-|
|**코드 맵**|예|만 코드 맵 읽기를 지원 필터링 코드 맵, 선택 항목에서 새 전송 그래프를 만들고 새 일반 노드를 추가 합니다.|-|
|**종속성 다이어그램**|예|종속성 다이어그램 읽기 지원만 합니다.|종속성 다이어그램 읽기 지원만 합니다.|
|**방향이 지정 된 그래프** (DGML 다이어그램)|예|예|예|
|**코드 복제본**|예|-|-|
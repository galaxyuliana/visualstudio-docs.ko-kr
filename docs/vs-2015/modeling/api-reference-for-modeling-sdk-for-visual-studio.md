---
title: Modeling SDK에 대 한 API 참조
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: reference
ms.assetid: 590c9a69-4e22-4841-bb23-f32e80ec1e76
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6a290227b120958b5bb3407393dcff33b247b20d
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68872018"
---
# <a name="api-reference-for-modeling-sdk-for-visual-studio"></a>Visual Studio용 모델링 SDK에 대한 API 참조
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 시각화 및 모델링 SDK는 DSL (도메인별 언어) 및 UML 도구가 빌드되는 플랫폼을 제공 합니다.

> [!NOTE]
> UML 모델링 API에 대 한 자세한 내용은 [Uml 모델링 확장성에 대 한 API 참조](../modeling/api-reference-for-uml-modeling-extensibility.md)를 참조 하세요. 텍스트 변환에 대 한 자세한 내용은 [T4 텍스트 변환 사용자 지정](../modeling/customizing-t4-text-transformation.md)을 참조 하세요.

 이 섹션에서는 이름이 "Microsoft.VisualStudio.Modeling"로 시작 하는 네임 스페이스에 대 한 참조 자료를 포함 합니다.

|네임스페이스|콘텐츠|
|---------------|-------------|
|<xref:Microsoft.VisualStudio.Modeling?displayProperty=fullName>|클래스는 DSL에서 정의 하는 모든 도메인 클래스의 기본 클래스는 ModelElement 등입니다.|
|<xref:Microsoft.VisualStudio.Modeling.Design?displayProperty=fullName>|DSL 정의의 일부를 형성 하는 클래스입니다.|
|<xref:Microsoft.VisualStudio.Modeling.Diagnostics?displayProperty=fullName>|모델 저장소 뷰어 및 성능 측정 도구입니다.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams?displayProperty=fullName>|DSL에서 정의 하는 모든 셰이프에의 기본 클래스인 ShapeElement 같은 클래스입니다.|
|<xref:Microsoft.VisualStudio.Modeling.Diagrams.ExtensionEnablement?displayProperty=fullName>|제스처 및 선택 메서드입니다.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition?displayProperty=fullName>|DSL 정의 디자이너의 API입니다.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.Design?displayProperty=fullName>|DSL 정의 디자이너의 내부 클래스입니다.|
|<xref:Microsoft.VisualStudio.Modeling.DslDefinition.ExtensionEnablement?displayProperty=fullName>|명령, 제스처 및 유효성 검사를 사용 하 여 DSL 디자이너를 확장할 수 있는 특성입니다.|
|<xref:Microsoft.VisualStudio.Modeling.Extensibility?displayProperty=fullName>|DSL 확장성을 구현 하는 모델 요소에 대 한 확장 메서드.|
|<xref:Microsoft.VisualStudio.Modeling.ExtensionEnablement?displayProperty=fullName>|확장 특성|
|<xref:Microsoft.VisualStudio.Modeling.Immutability?displayProperty=fullName>|읽기 전용으로 모델의 일부를 만들 수 있습니다.|
|[VisualStudio. 통합](/previous-versions/ee904412(v=vs.140))|Modelbus API를 사용 하면 다른 모델을 통합 합니다.|
|[VisualStudio를 선택 합니다.](/previous-versions/ee904394(v=vs.140))|사용자가 모델 및 Modelbus 참조를 만들 요소를 이동할 수 있는 대화 상자입니다.|
|`Microsoft.VisualStudio.Modeling.Integration.Picker.Hosting`|선택 서비스입니다.|
|[VisualStudio입니다.](/previous-versions/ee869435(v=vs.140))|용 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]Modelbus 어댑터 프레임 워크|
|[VisualStudio를 선택 합니다.](/previous-versions/ee886769(v=vs.140))|사용자가 모델 및 Modelbus 참조를 만들 요소를 이동할 수 있는 선택 대화 상자.|
|<xref:Microsoft.VisualStudio.Modeling.Shell?displayProperty=fullName>|Dsl과 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]간의 인터페이스입니다.|
|<xref:Microsoft.VisualStudio.Modeling.Shell.ExtensionEnablement?displayProperty=fullName>|바로 가기 (상황에 맞는) 메뉴 명령을 정의할 수 있습니다.|
|<xref:Microsoft.VisualStudio.Modeling.Validation?displayProperty=fullName>|유효성 검사 제약 조건을 정의할 수 있습니다.|

## <a name="see-also"></a>참고자료

- [UML 모델링 확장성을 위한 API 참조](../modeling/api-reference-for-uml-modeling-extensibility.md)
- [T4 텍스트 변환 사용자 지정](../modeling/customizing-t4-text-transformation.md)

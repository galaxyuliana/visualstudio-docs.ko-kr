---
title: 도메인별 언어 도구 사용자 인터페이스 개요
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.editor
helpviewer_keywords:
- Domain-Specific Language Tools, user interface
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 4cc5cf725b47c740bc14a57870e589c5de4e8c1b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54980429"
---
# <a name="overview-of-the-domain-specific-language-tools-user-interface"></a>도메인별 언어 도구 사용자 인터페이스 개요
Visual Studio에서 도메인 특정 언어 도구 (DSL 도구) 솔루션을 처음 열면 사용자 인터페이스는 다음 그림을 것과 비슷합니다.

 ![DSL 디자이너](../modeling/media/dsl_designer.png)

 다음 표에서 UI의 일부를 사용 하는 방법을 보여 줍니다.

|**요소**|**정의**|
|-|-|
|다이어그램|다이어그램에는 도메인 모델이 표시 됩니다.<br /><br /> 다이어그램에는 양측이 있습니다. 한쪽 모델에서 요소 형식을 정의합니다. 다른 쪽 모델 화면의 모양을 정의 합니다.|
|도구 상자|도메인 클래스를 추가 하 고 형식을 다이어그램에 셰이프 도구 상자에서 도구를 끕니다. 관계, 커넥터 및 도형 지도 추가 하려면 도구를 클릭 한 다음 다이어그램에서 소스 노드를 선택한 다음 대상 노드를 클릭 합니다.|
|DSL 탐색기|**DSL 탐색기** DSL 정의 활성 창 때 표시 됩니다. DSL을 트리로 표시 됩니다. DSL 탐색기를 사용 하면 모델의 다이어그램에 표시 되지 않는 기능을 편집할 수 있습니다. 도구 상자 항목을 추가 하 고 사용 하 여 유효성 검사 프로세스에서 전환할 수 있습니다 예를 들어 합니다 **DSL 탐색기**합니다.|
|DSL 정보 창|합니다 **DSL 정보** 창 모델의 요소, 요소 표시 방식 및 요소는 복사 하 고 삭제 하는 방법을 제어할 수 있도록 하는 도메인의 속성을 표시 합니다.<br /><br /> -기본적으로 **DSL 세부 정보** 창 옆에 표시 되는 **오류 목록** 하 고 **출력** windows.|

## <a name="the-domain-model-diagram"></a>도메인 모델 다이어그램
 도메인 모델 다이어그램은 두 부분으로 나뉩니다. 다이어그램의 한쪽에서는 모델의 요소 및 관계를 보여 줍니다. 다른 쪽에서는 모델을 표시 하는 하는 방법을 보여 줍니다. 요소 및 모델 다이어그램의 속성을 표시 하는 데 사용 되는 셰이프를 포함 합니다. 다음 그림은 다이어그램의 요소를 보여 줍니다.

 ![스윔 레인이 있는 DSL 디자이너](../modeling/media/dsl_desinger.png)

 다음 표에서 도메인 모델 다이어그램의 요소 중 일부를 설명 합니다.

|**용어**|**정의**|
|-|-|
|도메인 클래스|도메인 클래스는 모델의 요소 형식입니다.<br /><br /> 도메인 클래스는 둘 이상의 관계의 대상인 경우 다이어그램에서 두 번 이상 나타날 수 있습니다.<br /><br /> 도메인 클래스에 추가 하려면 도메인 클래스 도구를 끕니다를 **도구 상자** 에 **클래스 및 관계** 다이어그램의 측면입니다.|
|도메인 관계|도메인 관계는 모델에서 요소 간에 링크 유형의 있습니다.<br /><br /> *포함 관계* 대상 요소 소유 되었거나 원본 요소에 포함 된 되었음을 나타내며 실선으로 표시 됩니다. 모델의 모든 요소는 하나 포함 관계의 대상 해야 하므로 모델 트리를 형성 합니다. A *관계 참조* 파선된 선으로 나타나고 모델 요소 간의 일반 링크를 나타냅니다. 모든 요소 개수에 관계 없이 참조 링크를 포함할 수 있습니다.<br /><br /> 도구를 클릭 하 여 관계를 만들 합니다 **도구 상자**소스 도메인 클래스를 클릭 하 고 대상 클래스를 클릭 합니다.|
|모양 및 연결선|셰이프 모델 요소 DSL 다이어그램에 표시 되도록 하는 방법을 지정 하 고 커넥터 관계를 표시 하려면 사용할 수 있는 DSL 다이어그램에 줄을 지정 합니다.<br /><br /> 모양 또는 커넥터를 만들려면 도구를 끌어를 **다이어그램 요소** 다이어그램의 측면입니다.|
|모양 맵|도형 지도 표시 되는 도메인 클래스에 셰이프를 연결 하 고 도메인 모델 다이어그램이 나 표시 하는 도메인 관계에 커넥터를 선으로 나타납니다.|

## <a name="see-also"></a>참고 항목

- [도메인별 언어 도구 개요](../modeling/overview-of-domain-specific-language-tools.md)
- [도메인 특정 언어 도구 용어집](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)
- [도메인별 언어 사용자 지정 및 확장](../modeling/customizing-and-extending-a-domain-specific-language.md)
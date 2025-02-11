---
title: '방법: 콘텐츠 모델 뷰를 사용 하 여 노드의 콘텐츠 모델 검사 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
caps.latest.revision: 10
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 24ceb80c0ffd03e7c796b7a5d5abdc93f4c1c78d
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68179541"
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>방법: 콘텐츠 모델 뷰를 사용하여 노드의 콘텐츠 모델 검사
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목에서는 사용 하 여 노드를 탐색 하는 방법을 설명 합니다 [콘텐츠 모델 뷰](../xml-tools/content-model-view.md)합니다.  
  
### <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>콘텐츠 모델 뷰에서 새 XSD 파일을 만들고 루트 요소를 표시하려면  
  
1. 새 XML 스키마 파일을 만듭니다.  
  
2. 클릭 **보고 기본 XML 스키마 파일을 편집 하려면 XML 편집기를 사용 하 여** 시작 뷰.  
  
3. XML 스키마 샘플 코드를 복사 [샘플 XML 스키마: 구매 주문 스키마](../xml-tools/sample-xsd-file-purchase-order-schema.md) 붙여 넣어 기본적으로 새 XSD 파일에 추가 된 코드를 바꿉니다.  
  
4. 선택 합니다 `purchaseOrder` 마우스 오른쪽 단추로 클릭 하 여 스키마 탐색기에서 요소를 `purchaseOrder` XML 편집기에서 요소를 선택 하 고 **XML 탐색기에 표시**합니다.  
  
5. 마우스 오른쪽 단추로 클릭 합니다 `purchaseOrder` 선택한 XML 탐색기 **콘텐츠 모델 뷰로 표시**합니다.  
  
     콘텐츠 모델 뷰는 해당 디자인 화면에 `purchaseOrder` 요소를 표시합니다.  
  
6. 각 노드를 두 번 클릭하거나 각 노드 오른쪽에 있는 양방향 화살표를 클릭하여 `shipTo`, `billTo` 및 `items` 노드를 확장합니다.  
  
     이제 `purchaseOrder` 요소의 노드가 확장되고 요소의 콘텐츠 모델을 볼 수 있습니다.  
  
7. `purchaseOrder` 요소 아래의 노드를 클릭하고 이동 경로 탐색 막대를 확인하여 스키마 집합에서 선택한 노드가 위치한 곳을 봅니다.  
  
8. 클릭 합니다 **설명서 표시** 설명서를 전환 하려면 XSD 도구 모음 단추입니다. 또한 디자인 화면을 마우스 오른쪽 단추로 클릭하여 설명서를 표시하거나 숨길 수 있습니다.  
  
9. Rick 클릭 합니다 `purchaseOrder` 노드를 선택 **샘플 XML 생성** 에 XML 인스턴스 문서를 참조 하세요.

---
title: XML 스키마 디자이너 그래프 뷰
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 5881afde-3f24-4eb9-bff8-6cb3fc8aade7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 5a9ef512108ae31617257becf702c2b820c0ab85
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918646"
---
# <a name="graph-view"></a>그래프 보기

그래프 뷰에서는 전역 스키마 노드 및 노드 간 관계를 그래픽으로 표현합니다. 그래프 뷰에서는 디자인 화면에서 스키마 집합의 레이아웃을 변경할 수 없습니다. 그래프 뷰에는 XML 스키마 디자이너 도구 모음과 이동 경로 탐색 막대도 들어 있습니다.

다음 이미지에서는 디자인 화면에서 전역 노드가 6개인 그래프 뷰를 보여 줍니다.

![XML 스키마 디자이너 그래프 뷰](../xml-tools/media/xsddesigner_graphview.gif)

## <a name="design-surface"></a>디자인 화면

그래프 뷰의 디자인 화면에는 [XML 스키마 디자이너 작업 영역의](../xml-tools/xml-schema-designer-workspace.md)내용이 표시 됩니다. 작업 영역에 스키마 집합의 전역 노드가 포함되어 있는 경우 해당 노드는 그래프 뷰 디자인 화면에 표시되고 관계가 설정된 노드 사이에 화살표가 그려져 있습니다.

그래프 뷰에서 노드를 두 번 클릭 하면 XML 편집기가 표시 됩니다.

작업 영역에서 선택한 노드를 삭제 하려면 XSD 디자이너 도구 모음 또는 **delete** 키를 사용 합니다.

디자인 화면이 비어 있으면 XML 편집기, **Xml 스키마 탐색기**및 워터 마크가 표시 됩니다. *워터 마크* 는 모든 XSD 디자이너 뷰에 대 한 링크 목록입니다.

![XSD 디자이너, 그래프 뷰](../xml-tools/media/xsdgraphviewwatermark.gif)

스키마 집합에 오류가 있는 경우 목록 끝에 다음 텍스트가 표시 됩니다. "오류 목록를 사용 하 여 집합의 오류를 확인 하 고 수정 하십시오."

## <a name="breadcrumb-bar"></a>이동 경로 탐색 막대

그래프 뷰의 하단에 있는 이동 경로 탐색 막대에서는 스키마 집합에서 선택한 노드가 위치한 곳을 보여 줍니다. 여러 항목을 선택하면 이동 경로 탐색 막대가 비게 됩니다.

## <a name="context-right-click-menu"></a>상황에 맞는 (마우스 오른쪽 단추 클릭) 메뉴

다음 표에서는 그래프 뷰 디자인 화면의 모든 노드에 사용할 수 있는 옵션에 대해 설명합니다.

|옵션|Description|
|-|-----------------|
|**XML 스키마 탐색기에 표시**|스키마 탐색기에 포커스를 두고 스키마 집합 노드를 강조 표시합니다.|
|**그래프 뷰에 표시**|회색으로 표시된 그래프 뷰로 전환합니다.|
|**샘플 XML 생성**|전역 요소에만 사용할 수 있습니다. 전역 요소를 위한 샘플 XML 파일을 생성합니다.|
|**작업 영역 지우기**|작업 영역 및 디자인 화면을 지웁니다.|
|**작업 영역에서 제거**|작업 영역 및 디자인 화면에서 선택한 노드를 제거합니다.|
|**작업 영역에서 선택 항목을 제외한 모든 항목을 제거 합니다.**|작업 영역 및 디자인 화면에서 선택하지 않은 노드를 제거합니다.|
|**다이어그램을 이미지로 내보내기**|디자인 화면을 XPS 파일에 저장합니다.|
|**모두 선택**|디자인 화면에서 모든 노드를 선택합니다.|
|**코드 보기**|XML 편집기에서 선택한 노드를 포함 하는 파일을 엽니다. Xml **스키마 탐색기** 에서 선택한 항목도 xml 편집기에서 선택 됩니다.|
|**속성 창**|아직 열려 있지 않은 경우 **속성** 창을 엽니다. 이 창에서 노드에 대한 정보를 표시합니다.|

전역 요소에 대한 상황에 맞는 메뉴에는 위에서 설명한 일반 옵션 이외에도 다음 옵션이 있습니다.

|옵션|Description|
|-|-----------------|
|**형식 정의 추가**|기본 형식을 다이어그램에 추가합니다.|
|**모든 참조 추가**|요소를 참조하는 모든 노드를 추가하고 이러한 노드 간 관계를 나타내는 화살표를 그립니다.|
|**대체 그룹 멤버 추가**|모든 대체 그룹 멤버를 추가합니다. 요소가 대체 그룹의 헤드 또는 멤버인 경우 이 옵션이 뷰에 나타납니다.|
|**샘플 XML 생성**|전역 요소를 위한 샘플 XML 파일을 생성합니다.|

전역 단순 형식 및 전역 복합 형식에 대한 상황에 맞는 메뉴에는 위에서 설명한 일반 옵션 이외에도 다음 옵션이 있습니다.

|옵션|Description|
|-|-----------------|
|**기본 형식 추가**|선택한 형식이 전역 형식에서 파생된 경우 선택한 형식의 기본 형식을 추가합니다.|
|**모든 참조 추가**|선택한 형식의 모든 참조를 추가합니다. 여기에는 선택한 형식의 요소 및 특성과 선택한 형식에서 파생된 형식이 포함됩니다.|
|**모든 파생 형식 추가**|선택한 형식에서 직간접적으로 파생된 모든 형식을 추가합니다.|
|**모든 상위 항목 추가**|모든 부모(기본) 형식을 추가합니다.|

전역 그룹 및 특성 그룹에 대한 상황에 맞는 메뉴에는 위에서 설명한 일반 옵션 이외에도 다음 옵션이 있습니다.

|옵션|Description|
|-|-----------------|
|**모든 참조 추가**|그룹을 참조하는 모든 노드를 추가하고 이러한 노드 간 관계를 나타내는 화살표를 그립니다.|
|**모든 멤버 추가**|그룹의 모든 멤버를 추가하고 이러한 노드 간 관계를 나타내는 화살표를 그립니다.|

전역 특성에 대한 상황에 맞는 메뉴에는 위에서 설명한 일반 옵션 이외에도 다음 옵션이 있습니다.

|옵션|Description|
|-|-----------------|
|**모든 참조 추가**|그룹을 참조하는 모든 노드를 추가하고 이러한 노드 간 관계를 나타내는 화살표를 그립니다.|

## <a name="properties-window"></a>속성 창

상황에 맞는 (마우스 오른쪽 단추 클릭) 메뉴를 사용 하 여 처음에 **속성** 창을 엽니다. 기본적으로 **속성** 창은 Visual Studio의 오른쪽 아래 모서리에 표시 됩니다. 콘텐츠 모델 뷰에서 렌더링 되는 노드를 클릭 하면 해당 노드의 속성이 **속성** 창에 표시 됩니다.

## <a name="xsd-toolbar"></a>XSD 도구 모음

그래프 뷰가 활성화되면 다음 XSD 도구 모음 단추를 사용할 수 있습니다.

![XML 스키마 디자이너 도구 모음](../xml-tools/media/xsdgraphviewtoolbar.gif)

|옵션|Description|
|-|-----------------|
|**시작 뷰 표시**|[시작 뷰로](../xml-tools/start-view.md)전환 합니다. 이 보기는 바로 가기 키를 사용 하 여 액세스할 수 있습니다. **Ctrl**+**1**.|
|**콘텐츠 모델 뷰 표시**|[콘텐츠 모델 뷰로](../xml-tools/content-model-view.md)전환 합니다. 이 보기는 바로 가기 키를 사용 하 여 액세스할 수 있습니다. **Ctrl**+**2**.|
|**그래프 뷰 표시**|[그래프 뷰로](../xml-tools/graph-view.md)전환 합니다. 이 보기는 바로 가기 키를 사용 하 여 액세스할 수 있습니다. **Ctrl**+**3**.|
|**작업 영역 지우기**|작업 영역 및 디자인 화면을 지웁니다.|
|**작업 영역에서 제거**|작업 영역 및 디자인 화면에서 선택한 노드를 제거합니다.|
|**작업 영역에서 선택 항목을 제외한 모든 항목을 제거 합니다.**|작업 영역 및 디자인 화면에서 선택하지 않은 노드를 제거합니다. 이 옵션은 콘텐츠 모델 뷰 및 그래프 뷰에서 사용됩니다.|
|**왼쪽에서 오른쪽**|그래프 뷰의 레이아웃을 노드의 왼쪽에서 오른쪽 계층적 표현으로 변경합니다. 바로 가기 키를 사용 하 여이 옵션에 액세스할 수 있습니다.Alt+**오른쪽 화살표**|
|**오른쪽에서 왼쪽**|그래프 뷰의 레이아웃을 노드의 오른쪽에서 왼쪽 계층적 표현으로 변경합니다. 바로 가기 키를 사용 하 여이 옵션에 액세스할 수 있습니다.Alt+**왼쪽 화살표**|
|**위쪽에서 아래쪽**|그래프 뷰의 레이아웃을 노드의 위쪽에서 아래쪽 계층적 표현으로 변경합니다. 바로 가기 키를 사용 하 여이 옵션에 액세스할 수 있습니다.Alt+**아래쪽 화살표**입니다.|
|**아래쪽에서 위쪽**|그래프 뷰의 레이아웃을 노드의 아래쪽에서 위쪽 계층적 표현으로 변경합니다. 바로 가기 키를 사용 하 여이 옵션에 액세스할 수 있습니다.Alt+**위쪽 화살표**입니다.|

## <a name="panscroll"></a>이동/스크롤

스크롤 막대를 사용 하거나 **Ctrl** 키를 누른 상태에서 마우스를 클릭 하 고 끌어서 디자인 화면을 이동할 수 있습니다. 클릭하여 끌기를 통해 디자인 화면을 이동할 때 커서는 네 방향을 가리키는 네 개의 교차 화살표로 변경됩니다.

## <a name="undoredo"></a>실행 취소/다시 실행

그래프 뷰에서 다음 작업에 대한 실행 취소/다시 실행 기능이 사용됩니다.

- 끌어서 놓기를 통해 단일 노드 추가

- 스키마 탐색기 또는 시작 뷰 쿼리의 검색 결과 창에서 여러 노드 추가

- 단일 또는 여러 노드 삭제

## <a name="zoom"></a>Zoom

그래프 뷰의 오른쪽 아래 모퉁이에서 확대/축소를 사용할 수 있습니다.

확대/축소는 다음 방법으로 제어할 수 있습니다.

- 마우스를 그래프 뷰 화면 위로 가져갈 때 **Ctrl** 키를 누른 채 마우스 휠 회전

- 슬라이더 컨트롤 사용. 슬라이더에서는 현재 확대/축소 수준을 보여 줍니다.

확대/축소 슬라이더를 선택 하거나 마우스를 마우스로 가리키면 **Ctrl 키를 누르고** 마우스 휠을 사용 하 여 확대/축소할 수 있습니다. 다른 모든 시간에는 투명 합니다.

## <a name="xml-editor-integration"></a>XML 편집기 통합

노드를 클릭 하 고 코드 컨텍스트 보기 (마우스 오른쪽 단추 클릭) 메뉴를 사용 하 여 그래프 뷰와 XML 편집기 간에 앞뒤로 전환할 수 있습니다.

XML 편집기에서 스키마 집합을 변경 하는 경우 변경 내용은 그래프 뷰에서 동기화 됩니다. 자세한 내용은 [XML 편집기와의 통합](../xml-tools/integration-with-xml-editor.md)을 참조 하세요.

## <a name="see-also"></a>참고자료

- [Design Surface](../xml-tools/xml-schema-designer-workspace.md)
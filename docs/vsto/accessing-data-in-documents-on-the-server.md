---
title: 서버에 있는 문서의 데이터에 액세스
ms.date: 02/02/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Office development in Visual Studio], accessing on server
- data access [Office development in Visual Studio]
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: ef03779b541e4d6de99caf402793d62eeee68f3a
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54866227"
---
# <a name="access-data-in-documents-on-the-server"></a>서버에 있는 문서의 데이터에 액세스
  Microsoft Office Word 또는 Microsoft Office Excel의 개체 모델을 사용 하지 않고도 데이터를 문서 수준 사용자 지정에 대해 프로그래밍할 수 있습니다. 즉, 단어 없는 서버의 문서에 포함 된 데이터에 액세스할 수 있습니다 하거나 Excel이 설치 되어 있습니다. 예를 들어 서버에서 코드 (예를 들어는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지) 문서에서 데이터를 사용자 지정 하 고 최종 사용자에 게 사용자 지정된 된 문서를 보낼 수입니다. 최종 사용자가 문서를 열면 솔루션 어셈블리에 데이터 바인딩 코드가 문서에 사용자 지정된 데이터를 바인딩합니다. 문서의 데이터는 사용자 인터페이스에서 구분 하기 때문에 이것이 가능 합니다. 자세한 내용은 [문서 수준 사용자 지정에서 캐시 된 데이터](../vsto/cached-data-in-document-level-customizations.md)입니다.

 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]

## <a name="cache-data-for-use-on-a-server"></a>서버에서 사용 하기 위해 데이터를 캐시 합니다.
 문서에서 데이터 개체를 캐시 하려면 사용 하 여 표시 합니다 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 디자인 타임에 특성을 사용 하거나는 `StartCaching` 메서드 런타임에 호스트 항목의 합니다. 문서에서 데이터 개체를 캐시 하는 경우는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 문서에 저장 된 XML 문자열로 개체를 serialize 합니다. 개체 캐싱에 적합 한 특정 요구 사항을 충족 해야 합니다. 자세한 내용은 [데이터 캐시](../vsto/caching-data.md)합니다.

 서버 쪽 코드는 데이터 캐시의 모든 데이터 개체를 조작할 수 있습니다. 캐시 된 데이터 인스턴스에 바인딩되는 컨트롤은 데이터에 대 한 서버 쪽 변경 표시 되도록 자동으로 클라이언트에서 문서를 열 때 사용자 인터페이스를 통해 동기화 됩니다.

## <a name="access-data-in-the-cache"></a>데이터 캐시에 액세스
 예를 들어 콘솔 응용 프로그램, 응용 프로그램을 Windows Forms 또는 웹 페이지에서 사무실 외부에서 응용 프로그램에서 캐시 데이터에에서 액세스할 수 있습니다. 캐시 된 데이터에 액세스 하는 응용 프로그램에 완전 신뢰에 있어야 합니다. 부분 신뢰에는 웹 응용 프로그램을 삽입, 검색 하거나 Office 문서에서 캐시 된 데이터를 변경할 수 없습니다.

 데이터 캐시에 의해 노출 되는 컬렉션의 계층 구조를 통해 액세스할 수 합니다 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 의 속성을 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스:

- <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성이 반환을 <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>, 문서 수준 사용자 지정에서 캐시 된 데이터를 모두 포함 하는 합니다.

- 각 <xref:Microsoft.VisualStudio.Tools.Applications.CachedData> 하나 이상 포함 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 개체입니다. <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 모든 단일 클래스 내에 정의 된 캐시 된 데이터 개체를 포함 합니다.

- 각 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 하나 이상 포함 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 개체입니다. <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 단일 캐시 된 데이터 개체를 나타냅니다.

  다음 코드 예제에서는 캐시 된 문자열에 액세스 하는 방법에 설명 합니다 `Sheet1` 는 Excel 통합 문서 프로젝트의 클래스입니다. 이 예제는 제공 된 큰 예제의 일부는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> 메서드.

  [!code-csharp[Trin_ServerDocument#12](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#12)]
  [!code-vb[Trin_ServerDocument#12](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#12)]

## <a name="modify-data-in-the-cache"></a>캐시에 데이터를 수정 합니다.
 일반적으로 캐시 된 데이터 개체를 수정 하려면 다음 단계를 수행 합니다.

1.  개체의 새 인스턴스를 캐시 된 개체의 XML 표현을 deserialize 합니다. 사용 하 여 XML에 액세스할 수 있습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> 의 속성을 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 캐시 된 데이터 개체를 나타내는입니다.

2.  이 복사본을 변경 합니다.

3.  다음 옵션 중 하나를 사용 하 여 데이터 캐시로 다시 변경된 된 개체를 serialize 합니다.

    -   사용 하 여 변경 내용을 자동으로 serialize 하려는 경우는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 메서드. 이 메서드는를 **DiffGram** 형식으로 직렬화 하는 데 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 데이터 캐시에 데이터 집합 개체를 입력 합니다. 합니다 **DiffGram** 형식 오프 라인 문서의 데이터 캐시에서 변경 내용이 서버로 올바르게 전송 되는지 확인 합니다.

    -   캐시 된 데이터 변경에 대 한 고유한 serialization을 수행 하려는 경우를 작성할 수 있습니다에 직접는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> 속성입니다. 지정 합니다 **DiffGram** 형식을 사용 하는 경우를 <xref:System.Data.Common.DataAdapter> 데이터에 대 한 변경 내용으로 데이터베이스를 업데이트를 <xref:System.Data.DataSet>, <xref:System.Data.DataTable>, 형식화 된 데이터 집합 또는 합니다. 그렇지 않은 경우는 <xref:System.Data.Common.DataAdapter> 기존 행을 수정 하는 대신 새 행을 추가 하 여 데이터베이스를 업데이트 합니다.

### <a name="modify-data-without-deserializing-the-current-value"></a>현재 값을 역직렬화 하지 않고 데이터를 수정 합니다.
 경우에 따라 현재 값을 역직렬화 하지 않고 캐시 된 개체의 값을 수정 하는 것이 좋습니다. 예를 들어, 이렇게 하려면, 문자열 또는 정수와 같은 간단한 형식을 갖는 개체의 값을 변경 하는 경우 또는 캐시를 초기화 하는 경우 <xref:System.Data.DataSet> 서버의 문서에 있습니다. 이러한 경우에 사용할 수 있습니다는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 메서드 없이 캐시 된 개체의 현재 값을 역직렬화 합니다.

 다음 코드 예제에서는 캐시 된 문자열의 값을 변경 하는 방법에 설명 합니다 `Sheet1` 는 Excel 통합 문서 프로젝트의 클래스입니다. 이 예제는 제공 된 큰 예제의 일부는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> 메서드.

 [!code-csharp[Trin_ServerDocument#11](../vsto/codesnippet/CSharp/Trin_ServerDocument/Form1.cs#11)]
 [!code-vb[Trin_ServerDocument#11](../vsto/codesnippet/VisualBasic/Trin_ServerDocument/Form1.vb#11)]

### <a name="modify-null-values-in-the-data-cache"></a>데이터 캐시에서 null 값을 수정
 데이터 캐시 값을 가진 개체를 저장 하지 않습니다 **null** 문서를 저장 하 고 종료 하는 경우. 이 제한은 다음과 같은 결과가 캐시 된 데이터를 수정 하는 경우:

-   값 데이터 캐시에서 모든 개체를 설정 하는 경우 **null**, 모든 데이터 캐시의 개체에 자동으로 설정할 **null** 문서를 열 때 전체 데이터 캐시를 지울 수는 시점과 합니다 문서가 저장 되 고 닫힙니다. 데이터 캐시에서 모든 캐시 된 개체를 제거 하는, 및 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 컬렉션이 비어 있게 됩니다.

-   사용 하 여 솔루션을 빌드하면 **null** 데이터 캐시에서 개체를 사용 하 여 이러한 개체를 초기화 하려면를 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스 문서를 처음으로 열려 있는 모든 개체를 초기화 하는 확인 해야 합니다 데이터 캐시 합니다. 일부 개체를 초기화 하는 경우 개체의 모든 설정이 적용 됩니다 **null** 경우 문서를 열 및 문서를 저장 하 고 닫을 때 전체 데이터 캐시가 지워집니다.

## <a name="access-typed-datasets-in-the-cache"></a>형식화 된 데이터 집합 캐시에 액세스
 Office 솔루션에서와 Windows Forms 응용 프로그램과 같은 사무실 외부에서 응용 프로그램에서 형식화 된 데이터 집합의 데이터에 액세스 하려는 경우 또는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 프로젝트 둘 다에서 참조 되는 별도 어셈블리에서 형식화 된 데이터 집합을 정의 해야 프로젝트입니다. 사용 하 여 형식화 된 데이터 집합 각 프로젝트에 추가 하는 경우는 **데이터 원본 구성을** 마법사 또는 **데이터 집합 디자이너**,.NET Framework는 서로 다른 형식으로 두 프로젝트의 형식화 된 데이터 집합을 처리 . 형식화 된 데이터 집합을 만드는 방법에 대 한 자세한 내용은 참조 하세요. [만들기 및 Visual Studio에서 데이터 집합을 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)합니다.

## <a name="see-also"></a>참고자료

- [서버에 있는 문서의 데이터에 액세스](../vsto/accessing-data-in-documents-on-the-server.md)
- [문서 수준 사용자 지정의 캐시 된 데이터](../vsto/cached-data-in-document-level-customizations.md)
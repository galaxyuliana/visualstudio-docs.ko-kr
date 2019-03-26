---
title: '방법: XML 파일 편집'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 07fa3ecf-6345-4d30-9d85-d5ef5b083319
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b25eebad9efc70e4fda45131e232983e81961625
ms.sourcegitcommit: 489aca71046fb6e4aafd0a4509cd7dc149d707b1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/25/2019
ms.locfileid: "58415059"
---
# <a name="how-to-edit-xml-files"></a>방법: XML 파일 편집

XML 편집기는 XML 파일에 대 한 새 편집기입니다. 이 편집기는 독립 실행형 XML 파일 또는 Visual Studio 프로젝트에 연결된 파일에 사용할 수 있습니다. XML 편집기는 다음 파일 확장명을 사용 하 여 연결: *.config*, *.dtd*합니다 *.xml*를 *.xsd*, *.xdr*, *.xsl*합니다 *.xslt*, 및 *.vssettings*합니다. XML 편집기는 등록 된 특정 편집기 있으며 XML 또는 DTD 내용이 포함 된 다른 파일 형식 연결 이기도 합니다.

> [!NOTE]
> XHTML 문서는 HTML 편집기에서 처리됩니다.

XML 파일을 편집 하려면 편집 하려는 파일을 두 번 클릭 합니다.

## <a name="add-a-new-xml-file-to-a-project"></a>새 XML 파일을 프로젝트에 추가

1. **프로젝트** 메뉴에서 **새 항목 추가**합니다.

2. 선택 **XML 파일** 에서 합니다 **템플릿** 창입니다.

3. 파일 이름을 입력 합니다 **이름을** 필드 및 키를 눌러 **추가**합니다.

   XML 파일을 프로젝트에 추가 되 고 XML 편집기에서 열립니다. 파일에는 기본 XML 선언, `<?xml version="1.0" encoding="utf-8" ?>`이 포함됩니다.

## <a name="add-an-existing-xml-file-to-a-project"></a>기존 XML 파일을 프로젝트에 추가

1. **프로젝트** 메뉴에서 **기존 항목 추가**합니다.

   합니다 **기존 항목 추가** 대화 상자가 나타납니다.

2. XML 파일 및 키를 눌러 선택 **추가**합니다.

## <a name="create-a-new-xml-or-xslt-file"></a>새 XML 또는 XSLT 파일을 만듭니다

1. **파일** 메뉴에서 **새로 만들기**합니다.

   합니다 **새 파일** 대화 상자가 나타납니다.

2. 선택 **XML 파일** 새 XML 파일을 만들거나 선택 **XSLT 파일** 새 XSLT 스타일 시트를 만들려고 합니다.

3. **열기**를 클릭합니다.

## <a name="create-an-empty-project-for-xml-files"></a>XML 파일에 대 한 빈 프로젝트 만들기

::: moniker range="vs-2017"

1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

   **새 프로젝트** 대화 상자가 나타납니다.

2. 선택의 코드 언어를 선택 **빈 프로젝트**합니다.

3. **확인**을 클릭합니다.

::: moniker-end

::: moniker range=">=vs-2019"

1. **파일** 메뉴에서 **새로 만들기** > **프로젝트**합니다.

2. 입력 **빈 프로젝트** 템플릿 검색 상자에서 선택 합니다 **빈 프로젝트 (.NET Framework)** 템플릿과 클릭 **다음**합니다.

3. **만들기**를 클릭합니다.

::: moniker-end

4. 프로젝트에 XML 파일을 추가합니다.

   XML 편집기를이 프로젝트에 추가한 스키마를 찾아서 유효성 검사 및 IntelliSense XML, 스키마 또는이 프로젝트가 열려 있는 동안 편집 하면 XSLT 파일에 사용 합니다.

## <a name="see-also"></a>참고자료

- [XML 편집기](../xml-tools/xml-editor.md)
- [XML 문서 속성, 속성 창](../xml-tools/xml-document-properties-properties-window.md)
- [방법: XML 문서에서 XML 스키마 만들기](../xml-tools/how-to-create-an-xml-schema-from-an-xml-document.md)
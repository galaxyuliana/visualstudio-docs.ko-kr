---
title: '방법: XSLT에 중단점 사용'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7a569e3bc9d467b1cfce16d3836fdd1bb2a86e1c
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013693"
---
# <a name="how-to-use-breakpoints-with-xslt"></a>방법: XSLT에 중단점 사용

XSLT 스타일시트 또는 XML 소스 문서에서 중단점을 설정할 수 있습니다. 태그에 중단점을 설정한 경우 실행을 시작하면 소스 줄 정보가 있는 다음 문으로 중단점이 이동합니다.

자세한 내용은 참조 하세요. [디버깅 기본 사항: 중단점](../debugger/using-breakpoints.md)합니다.

## <a name="set-a-breakpoint-in-a-style-sheet"></a>스타일 시트에서 중단점을 설정 합니다.

중단점은 XSLT 스타일시트의 모든 시작 태그, 끝 태그 및 텍스트 노드에 설정할 수 있으며 스크립트 블록의 코드에 대해서도 설정할 수 있습니다.

### <a name="to-set-a-breakpoint-in-a-style-sheet"></a>스타일시트에서 중단점을 설정하려면

1.  XML 편집기에서 스타일시트를 엽니다.

2.  중단점 위치에 커서를 놓습니다, 마우스 오른쪽 단추로 클릭 하 고, 가리킨 **중단점**, 클릭 **중단점 삽입**합니다.

3.  찾아보기 단추를 클릭 (**...** )에 **입력** 문서 속성 창의 필드입니다.

4.  XML 소스 문서를 찾아 누릅니다 **열려**합니다.

     그러면 XSLT 변형에 사용되는 소스 문서 파일이 설정됩니다.

5.  클릭 합니다 **XSL 디버깅** XML 편집기 도구 모음 단추입니다.

## <a name="set-a-breakpoint-in-an-xml-source-document"></a>XML 소스 문서에서 중단점을 설정 합니다.

또한 중단점은 XML 소스 문서의 요소, 특성, 네임스페이스 노드, 주석, 처리 명령 및 텍스트 노드에 대해 설정할 수 있습니다. 그러나 부모 요소에서 상속되는 네임스페이스 노드나 문서 노드에 대해서는 중단점을 설정할 수 없습니다.

### <a name="to-set-a-breakpoint-in-an-xml-source-document"></a>XML 소스 문서에서 중단점을 설정하려면

1.  XML 편집기에서 XML 문서를 엽니다.

2.  중단점 위치에 커서를 놓습니다, 마우스 오른쪽 단추로 클릭 하 고, 가리킨 **중단점**, 클릭 **중단점 삽입**합니다.

3.  찾아보기 단추를 클릭 (**...** )에 **스타일 시트** 문서 속성 창의 필드입니다.

4.  XML 소스 문서를 찾아 누릅니다 **열려**합니다.

     그러면 XSLT 변형에 사용되는 소스 문서 파일이 설정됩니다.

5.  클릭 합니다 **XSL 디버깅** XML 편집기 도구 모음 단추입니다.

## <a name="see-also"></a>참고자료

- [연습: XSLT 스타일 시트 디버깅](../xml-tools/walkthrough-debug-an-xslt-style-sheet.md)
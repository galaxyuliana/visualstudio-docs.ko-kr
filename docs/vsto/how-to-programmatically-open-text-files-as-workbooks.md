---
title: '방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일 열기'
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- workbooks, opening text files as
- text [Office development in Visual Studio], text files
- text files, opening as workbooks
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: b0e333cd8ebb76df964c52ee48f4bde07e90fbaf
ms.sourcegitcommit: c0202a77d4dc562cdc55dc2e6223c062281d9749
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/24/2019
ms.locfileid: "54866206"
---
# <a name="how-to-programmatically-open-text-files-as-workbooks"></a>방법: 프로그래밍 방식으로 통합 문서로 텍스트 파일 열기
  통합 문서로 텍스트 파일을 열 수 있습니다. 열려는 텍스트 파일의 이름을 전달 해야 합니다. 시작에 대해 구문 분석 한 파일에 있는 데이터의 열 형식에는 행 수와 같은 여러 가지 선택적 매개 변수를 지정할 수 있습니다.  
  
 [!INCLUDE[appliesto_xlalldocapp](../vsto/includes/appliesto-xlalldocapp-md.md)]  
  
## <a name="example"></a>예제  
 [!code-csharp[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/CSharp/Trin_VstcoreExcelAutomationCS/Sheet1.cs#80)]
 [!code-vb[Trin_VstcoreExcelAutomation#80](../vsto/codesnippet/VisualBasic/Trin_VstcoreExcelAutomation/Sheet1.vb#80)]  
  
## <a name="compile-the-code"></a>코드 컴파일  
 이 예제에는 다음 구성 요소가 필요합니다.  
  
-   쉼표로 구분 된 텍스트 파일인 `Test.txt` 세 개 이상의 줄의 텍스트를 포함 하는 합니다.  
  
-   텍스트 파일 `Test.txt` C 드라이브에 저장  
  
## <a name="see-also"></a>참고자료  
 [통합 문서를 사용 하 여 작동 합니다.](../vsto/working-with-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 열기](../vsto/how-to-programmatically-open-workbooks.md)   
 [방법: 프로그래밍 방식으로 새 통합 문서 만들기](../vsto/how-to-programmatically-create-new-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 저장](../vsto/how-to-programmatically-save-workbooks.md)   
 [방법: 프로그래밍 방식으로 통합 문서 닫기](../vsto/how-to-programmatically-close-workbooks.md)   
 [Office 솔루션의 선택적 매개 변수](../vsto/optional-parameters-in-office-solutions.md)  

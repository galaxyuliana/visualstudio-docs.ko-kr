---
title: 속성 &lt;속성 이름이&gt; 연결에 참여 하 고 있으므로 삭제할 수 없습니다 &lt;연결 이름&gt; | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-data-tools
ms.topic: conceptual
ms.assetid: 389873cc-92dd-48da-bfca-0f6c8e0ae3c2
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 52dc1d42ab8fff879bd290fe1a9c9aa2ca0a08c0
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65700312"
---
# <a name="the-property-ltproperty-namegt-cannot-be-deleted-because-it-is-participating-in-the-association-ltassociation-namegt"></a>&lt;property name&gt; 속성은 &lt;association name&gt; 연결에 참여하고 있으므로 삭제할 수 없음
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

선택한 속성이 오류 메시지에 표시된 클래스 간 연결의 **연결 속성**으로 설정되었습니다. 속성이 데이터 클래스 간 연결에 참여 중인 경우에는 해당 속성을 삭제할 수 없습니다.  
  
 **연결 속성**을 데이터 클래스의 다른 속성으로 설정하면 원하는 속성을 삭제할 수 있습니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
1. O/R 디자이너에서 오류 메시지에 표시된 데이터 클래스를 연결하는 연결 선을 선택합니다.  
  
2. 해당 선을 두 번 클릭하여 **연결 편집기** 대화 상자를 엽니다.  
  
3. **연결 속성**에서 속성을 제거합니다.  
  
4. 속성 삭제를 다시 한 번 시도합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [방법: LINQ to SQL 클래스 (O/R 디자이너) 간 연결 (관계) 만들기](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 (O-r 디자이너) 만들기](https://msdn.microsoft.com/library/35aad4a4-2e8a-46e2-ae09-5fbfd333c233)   
 [LINQ to SQL](https://msdn.microsoft.com/library/73d13345-eece-471a-af40-4cc7a2f11655)

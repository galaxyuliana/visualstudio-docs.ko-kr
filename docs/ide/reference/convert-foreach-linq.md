---
title: foreach 루프를 LINQ로 변환
ms.date: 02/20/2019
ms.topic: reference
author: kendrahavens
ms.author: kehavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: eadad8fdbec990607450b374a32758547194f734
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58160276"
---
# <a name="convert-foreach-loop-to-linq"></a>foreach 루프를 LINQ로 변환

이 리팩터링은 다음에 적용됩니다.

- C#

**내용:** IEnumerables를 사용하여 foreach 루프를 LINQ 쿼리 또는 LINQ 호출 양식(LINQ 메서드라고도 함)으로 쉽게 변환할 수 있습니다.

**시기:** LINQ 쿼리로 읽는 것을 선호하는 IEnumerable을 사용하는 foreach 루프가 있는 경우

**이유:** 사용자는 foreach 루프보다 LINQ 구문을 사용하는 것을 선호하는 경우가 있습니다. [LINQ](/dotnet/csharp/programming-guide/concepts/linq/introduction-to-linq)를 사용하면 쿼리가 C#의 첫 번째 언어 구문이 됩니다. LINQ는 파일의 코드 양을 줄이고, 읽기 쉽게하며, 다른 데이터 원본이 유사한 쿼리 식 패턴을 갖도록 할 수 있습니다.

> [!NOTE]
> LINQ 구문은 일반적으로 foreach 루프보다 성능이 떨어집니다. LINQ 사용하여 코드의 가독성을 개선하는 경우에 발생할 수 있는 성능 저하를 인식하는 것이 좋습니다.

## <a name="convert-foreach-loop-to-linq-refactoring"></a>foreach 루프를 LINQ 리팩터링으로 변환

1. 커서를 `foreach` 키워드에 놓습니다.

    ![IEnumerable을 사용한 Foreach](media/convert-foreach-to-LINQ.png)

2. 줄의 임의 위치에서 **Ctrl**+**.** 를 눌러 **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.

   ![LINQ 메뉴로 변환](media/convert-foreach-to-LINQ-codefix.png)

3. **LINQ로 변환** 또는 **Linq(호출 양식)로 변환** 선택

   ![LINQ 쿼리 결과](media/convert-foreach-to-LINQ-result.png)
   
   ![LINQ 호출 양식 결과](media/convert-foreach-to-LINQ-callform-result.png)

## <a name="see-also"></a>참고 항목

- [리팩터링](../refactoring-in-visual-studio.md)
- [변경 내용 미리 보기](../../ide/preview-changes.md)
- [.NET 개발자를 위한 팁](../../ide/visual-studio-2017-for-dotnet-developers.md)
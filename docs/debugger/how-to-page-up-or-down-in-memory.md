---
title: '방법: 페이지 위쪽에서에서 위 또는 아래로 메모리 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
helpviewer_keywords:
- debugger, paging up or down in memory
- memory, paging up or down
- Disassembly window, viewing memory space
- Memory window, paging up or down in memory
ms.assetid: 50b30a68-66f6-43f8-a48b-59ce12c95471
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4b8452100eb744d019c0f4c8d5e62566ac761210
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62894023"
---
# <a name="how-to-page-up-or-down-in-memory"></a>방법: 메모리에서 페이지 위 또는 아래로 이동

**메모리** 창이나 **디스어셈블리** 창에서 메모리 내용을 볼 때 세로 스크롤 막대를 사용하여 메모리 공간에서 위나 아래로 이동할 수 있습니다.

### <a name="to-page-up-or-down-in-memory"></a>메모리에서 페이지 위나 아래로 이동하려면

1. 페이지 아래로 이동하려면(상위 메모리 주소로 이동) 스크롤 상자 아래쪽의 세로 스크롤 막대를 클릭합니다.

2. 페이지 위로 이동하려면(하위 메모리 주소로 이동) 스크롤 상자 위쪽 세로 스크롤 막대를 클릭합니다.

   이때 세로 스크롤 막대는 일반적인 방식으로 작동하지 않습니다. 오늘날 사용되는 컴퓨터는 주소 공간이 매우 크므로 스크롤 막대의 엄지 단추를 임의의 위치로 드래그하면 현재 위치와 방향을 잃기 쉽습니다. 이러한 이유로 스크롤 상자는 "스프링이 달려 있는 것처럼" 항상 스크롤 막대 중앙에 놓이게 됩니다. 네이티브 코드 애플리케이션에서 페이지 위나 아래로는 이동할 수 있지만 자유롭게 스크롤할 수는 없습니다.

   관리되는 애플리케이션에서는 디스어셈블리가 하나의 함수로 제한되므로 평소처럼 스크롤할 수 있습니다.

   상위 주소가 창 아래쪽에 나타나므로 상위 주소를 확인하려면 아래쪽으로 이동해야 합니다.

#### <a name="to-move-up-or-down-one-instruction"></a>명령 위/아래로 이동하려면

- 세로 스크롤 막대 맨 위나 맨 아래에 있는 화살표를 클릭합니다.

## <a name="see-also"></a>참고 항목
- [메모리 창](../debugger/memory-windows.md)
- [방법: 디스어셈블리 창 사용](../debugger/how-to-use-the-disassembly-window.md)
- [디버거에서 데이터 보기](../debugger/viewing-data-in-the-debugger.md)
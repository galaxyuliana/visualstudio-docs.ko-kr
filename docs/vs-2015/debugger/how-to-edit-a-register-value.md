---
title: '방법: 레지스터 값 편집 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
f1_keywords:
- vs.debug.register.edit
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- Registers window, editing register values
- register values
ms.assetid: e27b6bd8-e6d4-4f1d-8a86-9f4047bb1167
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 7566d3a89ff27cc473b9352c7e0f02492dc736d1
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58985780"
---
# <a name="how-to-edit-a-register-value"></a>방법: 레지스터 값 편집
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

레지스터 창은 **옵션** 대화 상자의 **디버깅** 노드에서 주소 수준 디버깅을 활성화한 경우에만 사용할 수 있습니다.  
  
### <a name="to-change-the-value-of-a-register"></a>레지스터 값을 변경하려면  
  
1.  **레지스터** 창에서 탭 키 또는 마우스를 사용하여 변경하려는 값으로 삽입 지점을 이동합니다. 입력하기 시작할 때 덮어 쓰려는 값 앞에 커서가 있어야 합니다.  
  
2.  새 값을 입력합니다.  
  
    > [!CAUTION]
    >  레지스터 값을 변경하면(특히 EIP 및 EBP 레지스터에서) 프로그램 실행에 변경된 값이 적용됩니다.  
  
    > [!CAUTION]
    >  부동 소수점 값을 편집하면 소수 부분이 10진수에서 이진수로 변환되면서 약간의 오차가 발생할 수 있습니다. 겉보기에 변화가 없는 편집 작업을 수행하는 경우에도 부동 소수점 변수의 LSB 중 일부가 변경될 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: 레지스터 창 사용](../debugger/how-to-use-the-registers-window.md)

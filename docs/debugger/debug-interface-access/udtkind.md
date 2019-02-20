---
title: UdtKind | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- UdtKind enumeration
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bb649915179bc6e6b767970150df99caff306b4c
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56317733"
---
# <a name="udtkind"></a>UdtKind
다양을 한 사용자 정의 형식 (UDT)에 대해 설명합니다.

## <a name="syntax"></a>구문

```C++
enum UdtKind {
    UdtStruct,
    UdtClass,
    UdtUnion,
    UdtInterface
};
```

## <a name="elements"></a>요소
UdtStruct  
UDT에는 구조입니다.

UdtClass  
UDT는 클래스입니다.

UdtUnion  
UDT는 공용 구조체입니다.

UdtInterface  
UDT 인터페이스입니다.

## <a name="remarks"></a>주의
이 열거형의 값에서 반환 되는 [idiasymbol:: Get_udtkind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: cvconst.h

## <a name="see-also"></a>참고 항목
[열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)

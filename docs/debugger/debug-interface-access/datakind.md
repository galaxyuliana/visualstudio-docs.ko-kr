---
title: DataKind | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- DataKind enumeration
ms.assetid: b64be708-22d6-4360-99e7-8f4e6b196de7
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: bf8e59bf79355b4e610091ac8662b8d2a01af322
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318682"
---
# <a name="datakind"></a>DataKind
데이터 값의 특정 범위를 나타냅니다.

## <a name="syntax"></a>구문

```C++
enum DataKind {
    DataIsUnknown,
    DataIsLocal,
    DataIsStaticLocal,
    DataIsParam,
    DataIsObjectPtr,
    DataIsFileStatic,
    DataIsGlobal,
    DataIsMember,
    DataIsStaticMember,
    DataIsConstant
};
```

## <a name="elements"></a>요소
DataIsUnknown  
데이터 기호를 확인할 수 없습니다.

DataIsLocal  
데이터 항목에는 지역 변수입니다.

DataIsStaticLocal  
데이터 항목에는 정적 지역 변수입니다.

DataIsParam  
데이터 항목에는 정식 매개 변수입니다.

DataIsObjectPtr  
데이터 항목 개체 포인터는 (`this`).

DataIsFileStatic  
데이터 항목에는 파일 범위 변수입니다.

DataIsGlobal  
데이터 항목에는 전역 변수입니다.

DataIsMember  
데이터 항목 개체 멤버 변수입니다.

DataIsStaticMember  
데이터 항목에는 정적 클래스 변수입니다.

DataIsConstant  
데이터 항목에는 상수 값입니다.

## <a name="remarks"></a>주의
이 열거형의 값에서 반환 되는 [idiasymbol:: Get_datakind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md) 메서드.

## <a name="requirements"></a>요구 사항
헤더: cvconst.h

## <a name="see-also"></a>참고 항목
[열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSymbol::get_dataKind](../../debugger/debug-interface-access/idiasymbol-get-datakind.md)

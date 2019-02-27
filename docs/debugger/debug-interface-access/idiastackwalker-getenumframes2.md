---
title: IDiaStackWalker::getEnumFrames2 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaStackWalker2::getEnumFrames2 method
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 35886ea0456426c30c44d5fd8e90399d4a2143ef
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56642757"
---
# <a name="idiastackwalkergetenumframes2"></a>IDiaStackWalker::getEnumFrames2
특정 플랫폼 형식에 대 한 스택 프레임 열거자를 검색합니다.

## <a name="syntax"></a>구문

```C++

      HRESULT getEnumFrames2( 
   enum  CV_CPU_TYPE_e    cpuid,
   IDiaStackWalkHelper*   pHelper,
   IDiaEnumStackFrames**  ppEnum
);
```

#### <a name="parameters"></a>매개 변수
 `cpuid`

[in] 값을 [CV_CPU_TYPE_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 플랫폼 유형을 지정 하는 열거형입니다.

 `pHelper`

[in] 도우미 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) 개체입니다.

 `ppEnum`

[out] 반환 된 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md) 목록이 포함 된 개체 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md) 개체입니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="remarks"></a>주의
 X86만 스택 프레임 목록을 가져오려면 플랫폼을 호출 합니다 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) 메서드.

## <a name="see-also"></a>참고 항목
- [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)
- [CV_CPU_TYPE_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md)
- [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)
- [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
- [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)
---
title: METADATA_ADDRESS_ARRAYELEM | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- METADATA_ADDRESS_ARRAYELEM
helpviewer_keywords:
- METADATA_ADDRESS_ARRAYELEM structure
ms.assetid: 24321be5-7c17-4038-82a1-c20a2b68ff3c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 900ac5f6dec739574af27601e2b3a26d6041da55
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54917213"
---
# <a name="metadataaddressarrayelem"></a>METADATA_ADDRESS_ARRAYELEM
이 구조 배열 내에서 배열 요소를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_ARRAYELEM {  
   _mdToken tokMethod;  
   DWORD    dwIndex;  
} METADATA_ADDRESS_ARRAYELEM;  
```  
  
```csharp  
public struct METADATA_ADDRESS_ARRAYELEM {  
   public int  tokMethod;  
   public uint dwIndex;  
}  
```  
  
## <a name="terms"></a>용어  
 tokMethod  
 배열의 ID이이 요소는 부분입니다.  
  
 [C + +] `_mdToken` 되는 `typedef` 32 비트 `int`합니다.  
  
 dwIndex  
 배열 내에서이 요소의 인덱스입니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 공용 구조체의 일부인를 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 경우 구조체를 `dwKind` 필드를 `DEBUG_ADDRESS_UNION` 구조로 설정 되어 `ADDRESS_KIND_ARRAYELEM` (의 값을 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형)입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
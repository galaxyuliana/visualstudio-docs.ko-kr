---
title: METADATA_ADDRESS_RETVAL | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- METADATA_ADDRESS_RETVAL
helpviewer_keywords:
- METADATA_ADDRESS_RETVAL structure
ms.assetid: 5b0ec0fb-84b3-4ce7-8e24-becf3d881d7d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 89e10bac9db8782c117e114b02e4ff73a3693518
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55006101"
---
# <a name="metadataaddressretval"></a>METADATA_ADDRESS_RETVAL
이 구조는 메서드 또는 함수에서 반환 값을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_RETVAL {  
   _mdToken tokMethod;  
   DWORD    dwCorType;  
   DWORD    dwSigSize;  
   BYTE     rgSig[10];  
} METADATA_ADDRESS_RETVAL;  
```  
  
```csharp  
public struct METADATA_ADDRESS_RETVAL {  
   public int    tokMethod;  
   public uint   dwCorType;  
   public uint   dwSigSize;  
   public byte[] rgSig;  
}  
```  
  
## <a name="terms"></a>용어  
 tokMethod  
 메서드의 반환 값이에 대 한 ID입니다.  
  
 dwCorType  
 반환 값의 기본 형식입니다. 값을 `CorElementType` 열거형에 정의 된는 [!INCLUDE[dnprdnshort](../../../code-quality/includes/dnprdnshort_md.md)] SDK corhdr.h 파일입니다.  
  
 dwSigSize  
 반환 값 서명의 크기 (에 저장 된 `rgSig`).  
  
 rgSig  
 반환 값의 시그니처를 형성 하는 바이트 배열입니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 공용 구조체의 일부인를 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 경우 구조체를 `dwKind` 필드를 `DEBUG_ADDRESS_UNION` 구조로 설정 되어 `ADDRESS_KIND_RETVAL` (의 값을 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형)입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG_ADDRESS_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS_KIND](../../../extensibility/debugger/reference/address-kind.md)
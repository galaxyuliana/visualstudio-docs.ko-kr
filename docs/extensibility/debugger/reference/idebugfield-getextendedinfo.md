---
title: IDebugField::GetExtendedInfo | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugField::GetExtendedInfo
helpviewer_keywords:
- IDebugField::GetExtendedInfo method
ms.assetid: 46c0dd4d-4fd5-4efd-a908-71e4248e8e8d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 915cf272a592628f6d25ebf04edd4309bceccfb3
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55007792"
---
# <a name="idebugfieldgetextendedinfo"></a>IDebugField::GetExtendedInfo
이 메서드 확장 필드에 대 한 정보를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetExtendedInfo(   
   REFGUID guidExtendedInfo,  
   BYTE**  prgBuffer,  
   DWORD*  pdwLen  
);  
```  
  
```csharp  
int GetExtendedInfo(  
   ref Guid guidExtendedInfo,   
   IntPtr[] prgBuffer,   
   ref uint pdwLen  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `guidExtendedInfo`  
 [in] 반환 될 정보를 선택 합니다. 올바른 값은 다음과 같습니다.  
  
|값|설명|  
|-----------|-----------------|  
|`guidConstantValue`|바이트의 시퀀스로 값입니다.|  
|`guidConstantType`|형식 시그니처는 형식입니다.|  
  
 `prgBuffer`  
 [out] 확장된 정보를 반환합니다.  
  
 `pdwLen`  
 [out에서] 확장 정보의 크기 (바이트)에서 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 현재이 메서드는 형식 또는 상수 값을 반환합니다. 호출자에 반환 되는 버퍼를 해제 해야 합니다 `prgBuffer` COM의 호출 `CoTaskMemFree` 함수 (c + +) 또는 <xref:System.Runtime.InteropServices.Marshal.FreeCoTaskMem%2A> (C#).  
  
## <a name="see-also"></a>참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
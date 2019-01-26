---
title: PDB_TYPE | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- PDB_TYPE
helpviewer_keywords:
- PDB_TYPE structure
ms.assetid: 1c1bb772-77d6-4870-90b2-fd9247d0004e
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 82cea5721a68c9c4a11a53caa7c7db89b69ac72a
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941894"
---
# <a name="pdbtype"></a>PDB_TYPE
이 구조는 PDB 기호에서 가져온 필드 형식에 대 한 정보를 지정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef struct _tagTYPE_PDB {  
   ULONG32 ulAppDomainID;  
   GUID    guidModule;  
   DWORD   symid;  
} PDB_TYPE;  
```  
  
```csharp  
public struct PDB_TYPE {  
   public uint ulAppDomainID;  
   public Guid guidModule;  
   public uint symid;  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
 ulAppDomainID  
 기호 가져온 응용 프로그램의 ID입니다. 이 응용 프로그램의 인스턴스를 고유 하 게 식별에 사용 됩니다.  
  
 guidModule  
 이 필드를 포함 하는 모듈의 GUID입니다.  
  
 symid  
 이 필드에 해당 하는 기호 ID입니다.  
  
## <a name="remarks"></a>설명  
 이 구조체의 공용 구조체의 일부분으로 표시를 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md) 경우 구조체를 `dwKind` 필드를 `TYPE_INFO` 구조로 설정 되어 `TYPE_KIND_PDB` (의 값을 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md) 열거형)입니다.  
  
## <a name="requirements"></a>요구 사항  
 헤더: sh.h  
  
 네임스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## <a name="see-also"></a>참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [TYPE_INFO](../../../extensibility/debugger/reference/type-info.md)   
 [dwTYPE_KIND](../../../extensibility/debugger/reference/dwtype-kind.md)
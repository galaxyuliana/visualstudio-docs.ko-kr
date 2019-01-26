---
title: IDebugProgramHost2::GetHostName | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProgramHost2::GetHostName
helpviewer_keywords:
- IDebugProgramHost2::GetHostName
ms.assetid: 48bbb089-e59a-471a-9965-24b42a8dabf3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 040602eeca784ac6265403f615f9234864715949
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54923271"
---
# <a name="idebugprogramhost2gethostname"></a>IDebugProgramHost2::GetHostName
제목, 이름, 또는이 프로그램의 호스팅 프로세스의 파일 이름을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetHostName(   
   DWORD dwType,  
   BSTR* pbstrHostName  
);  
```  
  
```csharp  
int GetHostName(   
   uint dwType,  
   out string pbstrHostName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dwType`  
 [in] 값을 [GETHOSTNAME_TYPE](../../../extensibility/debugger/reference/gethostname-type.md) 열거형입니다.  
  
 `pbstrHostName`  
 [out] 호스팅 프로세스의 요청 된 이름을 반환합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 이 메서드의 일반적인 구현은에 `dwType` 매개 변수는 무시 되 고 호스트 컴퓨터의 이름을 반환 됩니다. 다른 가능한 구현은 전달 하는 것은 `dwType` 호출에 매개 변수를 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md) 메서드 이름을 가져옵니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugProgramHost2](../../../extensibility/debugger/reference/idebugprogramhost2.md)   
 [GetHostName](../../../extensibility/debugger/reference/idebugprogramnode2-gethostname.md)
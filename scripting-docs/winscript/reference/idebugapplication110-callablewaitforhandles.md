---
title: IDebugApplication110::CallableWaitForHandles | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
helpviewer_keywords:
- IDebugApplication110::CallableWaitForHandles
ms.assetid: 02e79b60-0d67-47f9-bf78-b65a02c9c014
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ac5482924288e52895398084aa4f5ab44e151a66
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155370"
---
# <a name="idebugapplication110callablewaitforhandles"></a>IDebugApplication110::CallableWaitForHandles
신호를 받을 수 있도록 하는 동안 지정 된 핸들에 대 한 대기 크로스 스레드 호출이이 스레드를 게시 합니다. 디버거 스레드에서이 메서드를 호출 해야 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md) 는 PDM v11.0에 의해 구현 된 이상. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CallableWaitForHandles([in] DWORD handleCount, [in, size_is(handleCount)] const HANDLE* pHandles, [out] DWORD* pIndex);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `handleCount`  
 대기 핸들의 수입니다.  
  
 `pHandles`  
 집합에 대 한 대기에 대 한 핸들입니다.  
  
 `pIndex`  
 HRESULT 값이 인덱스 S_OK `pHandles` 신호를 받은 핸들에 대 한 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md)
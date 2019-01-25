---
title: IRemoteDebugApplicationEx:RevokeBreak | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- IRemoteDebugApplicationEx:RevokeBreak
apilocation:
- scrobj.dll
helpviewer_keywords:
- IRemoteDebugApplicationEx:RevokeBreak
ms.assetid: 1f077860-0a39-4ec9-b676-ae0712819c7b
caps.latest.revision: 5
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd014defff65ee4b29566219ea3bc04ce0cc3a4e
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54754561"
---
# <a name="iremotedebugapplicationexrevokebreak"></a>IRemoteDebugApplicationEx:RevokeBreak

Break 명령을 취소합니다.

## <a name="syntax"></a>구문

```cpp
HRESULT RevokeBreak( );
```

### <a name="parameters"></a>매개 변수

없음

## <a name="return-value"></a>반환 값

이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.

|값|설명|
|-----------|-----------------|
|`S_OK`|메서드가 성공했으며|

## <a name="see-also"></a>참고자료

- [IRemoteDebugApplicationEx 인터페이스](iremotedebugapplicationex-interface.md)
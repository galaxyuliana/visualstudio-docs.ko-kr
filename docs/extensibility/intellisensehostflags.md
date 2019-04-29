---
title: IntelliSenseHostFlags | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 882410d68c671a83b13bd14026e5bea4c31cb37e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62861637"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
IntelliSense 호스트 플래그를 지정합니다.

## <a name="syntax"></a>구문

```cpp
enum IntellisenseHostFlags
{
    IHF_READONLYCONTEXT      = 0x00000001
    IHF_NOSEPARATESUBJECT    = 0x00000002
    IHF_SINGLELINESUBJECT    = 0x00000004
    IHF_FORCECOMMITTOCONTEXT = 0x00000008
    IHF_OVERTYPE             = 0x00000010
};
```

### <a name="parameters"></a>매개 변수

|멤버|설명|
|-------------|-----------------|
|`IHF_READONLYCONTEXT`|상황에 맞는 버퍼는 읽기 전용입니다.|
|`IHF_NOSEPARATESUBJECT`|제목 텍스트가 없습니다. 상황에 맞는 버퍼에 IntelliSense 대상 (의미 `!IHF_READONLYCONTEXT`).|
|`IHF_SINGLELINESUBJECT`|제목 텍스트는 다중 명령줄 수 없습니다.|
|`IHF_FORCECOMMITTOCONTEXT`|`CanCommitIntoReadOnlyBuffer`와 동일합니다.|
|`IHF_OVERTYPE`|겹쳐쓰기 모드에서 주체 또는 상황에 맞는) (에서 편집 해야 합니다.|

## <a name="requirements"></a>요구 사항
 SingleFileeditor.idl

## <a name="see-also"></a>참고자료
- <xref:Microsoft.VisualStudio.TextManager.Interop>
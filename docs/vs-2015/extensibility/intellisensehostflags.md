---
title: IntelliSenseHostFlags | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
f1_keywords:
- IntellisenseHostFlags
helpviewer_keywords:
- IntelliSense, IntellisenseHostFlags enumeration
- IntellisenseHostFlags enumeration
ms.assetid: 0930640b-eb84-48ef-a8f7-d4268f55c99c
caps.latest.revision: 7
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 12945998b215e9082591fad514bd9c16ab789405
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58980935"
---
# <a name="intellisensehostflags"></a>IntelliSenseHostFlags
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

IntelliSense 호스트 플래그를 지정합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp#  
enum IntellisenseHostFlags  
{  
    IHF_READONLYCONTEXT      = 0x00000001  
    IHF_NOSEPARATESUBJECT    = 0x00000002  
    IHF_SINGLELINESUBJECT    = 0x00000004  
    IHF_FORCECOMMITTOCONTEXT = 0x00000008  
    IHF_OVERTYPE             = 0x00000010  
};  
```  
  
#### <a name="parameters"></a>매개 변수  
  
|멤버|설명|  
|-------------|-----------------|  
|`IHF_READONLYCONTEXT`|상황에 맞는 버퍼는 읽기 전용입니다.|  
|`IHF_NOSEPARATESUBJECT`|제목 텍스트가 없습니다. 상황에 맞는 버퍼에 IntelliSense 대상 (의미 `!IHF_READONLYCONTEXT`).|  
|`IHF_SINGLELINESUBJECT`|제목 텍스트는 다중 명령줄 수 없습니다.|  
|`IHF_FORCECOMMITTOCONTEXT`|`CanCommitIntoReadOnlyBuffer`와 동일합니다.|  
|`IHF_OVERTYPE`|겹쳐쓰기 모드에서 주체 또는 상황에 맞는) (에서 편집 해야 합니다.|  
  
## <a name="requirements"></a>요구 사항  
 SingleFileeditor.idl  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.TextManager.Interop>

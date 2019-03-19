---
title: PROFILER_HEAP_OBJECT 구조체 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9f35362c-6856-4cfb-b990-031a156a58eb
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a1652c6ebffff88782ffcc879158a5142f22395d
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58151195"
---
# <a name="profilerheapobject-structure"></a>PROFILER_HEAP_OBJECT 구조체
힙 개체에서 수집한 나타냅니다 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef struct _PROFILER_HEAP_OBJECT  
{  
    UINT size;    union {        PROFILER_HEAP_OBJECT_ID objectId;        PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;    };    PROFILER_HEAP_OBJECT_NAME_ID typeNameId;    USHORT flags;     USHORT optionalInfoCount;} PROFILER_HEAP_OBJECT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|형식|설명|  
|------------|----------|-----------------|  
|objectId|[PROFILER_HEAP_OBJECT_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|힙 개체의 ID입니다.|  
|externalObjectAddress|[PROFILER_EXTERNAL_OBJECT_ADDRESS 형식](../../winscript/reference/profiler-external-object-address-type.md)|JavaScript 힙 외부에 있는 c + +에서 할당 된 개체와 같은 개체의 외부 개체 주소입니다.|  
|typeNameId|[PROFILER_HEAP_OBJECT_NAME_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md)|힙 개체 형식 이름의 ID에서 검색 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)합니다. 중 하나만 `externalObjectAddress` 나 `typeName` 에 따라는 `flags` 값입니다.|  
|플래그|[PROFILER_HEAP_OBJECT_FLAGS 열거형](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|힙 개체에 대 한 기본 정보를 포함 하는 플래그입니다.|  
|optionalInfoCount|USHORT|수가 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 힙 개체에 사용할 수 있는 레코드입니다.|
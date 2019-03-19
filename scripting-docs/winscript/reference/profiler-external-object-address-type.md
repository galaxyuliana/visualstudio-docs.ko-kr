---
title: PROFILER_EXTERNAL_OBJECT_ADDRESS 형식 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c9642a4a-f1fd-408a-9de6-e51562337bf1
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b5708dfb0ad5e419f217d6d06a3c2b039d55b35
ms.sourcegitcommit: d3a485d47c6ba01b0fc9878cbbb7fe88755b29af
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2019
ms.locfileid: "58155997"
---
# <a name="profilerexternalobjectaddress-type"></a>PROFILER_EXTERNAL_OBJECT_ADDRESS 형식
JavaScript 힙 외부에 있는 c + +에서 할당 된 개체와 같은 개체의 외부 개체 주소입니다. 레지스트리에 [PROFILER_HEAP_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 하 고 [PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp
typedef void* PROFILER_EXTERNAL_OBJECT_ADDRESS;  
```
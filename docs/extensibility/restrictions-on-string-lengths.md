---
title: 문자열 길이 제한 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control plug-ins, restrictions on string lengths
ms.assetid: 877173d2-ca27-43b3-b1f4-8379f7c5e268
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 679737b9590cd018f0de16298391351aedb0ac94
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54929954"
---
# <a name="restrictions-on-string-lengths"></a>문자열 길이 제한
원본 제어 플러그 인 API는 다양 한 함수에서 사용 되는 문자열의 길이 제한 합니다.  
  
## <a name="string-length-values"></a>문자열 길이 값  
  
|상수|값|  
|--------------|-----------|  
|`SCC_NAME_LEN`|31|  
|`SCC_AUXLABEL_LEN`|31|  
|`SCC_USER_LEN`|31|  
|`SCC_PRJPATH_LEN`|300|  
  
> [!NOTE]
>  길이 종료 포함 되지 않습니다 `null`합니다. "_LEN" 대신 "크기 _s" 접미사가 있는 다른 상수에는 종료를 위한 공간이 포함 수행 `null`합니다.  
  
|상수|값|  
|--------------|-----------|  
|SCC_NAME_SIZE|32|  
|SCC_AUXLABEL_SIZE|32|  
|SCC_USER_SIZE|32|  
|SCC_PRJPATH_SIZE|301|  
  
## <a name="see-also"></a>참고자료  
 [원본 제어 플러그 인](../extensibility/source-control-plug-ins.md)
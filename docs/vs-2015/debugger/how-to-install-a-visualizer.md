---
title: '방법: 시각화 도우미 설치 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: conceptual
dev_langs:
- FSharp
- VB
- CSharp
- C++
- JScript
- VB
- CSharp
- C++
helpviewer_keywords:
- debugger, visualizers
- visualizers, installing
ms.assetid: 3310ef43-515c-4d97-b0f9-51047247d3da
caps.latest.revision: 29
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2e223831b30f784094a2affa5cebb314cc6e997f
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60059710"
---
# <a name="how-to-install-a-visualizer"></a>방법: 시각화 도우미 설치
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

시각화 도우미를 만든 후에는 [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]에서 사용할 수 있도록 이 시각화 도우미를 설치해야 합니다. 시각화 도우미를 설치하는 과정은 간단합니다.  
  
> [!NOTE]
>  **Store** 앱에만 표준 텍스트, HTML, XML 및 JSON 시각화 도우미는 지원 합니다. 사용자가 만든 사용자 지정 시각화 도우미는 지원되지 않습니다.  
  
### <a name="to-install-a-visualizer"></a>시각화 도우미를 설치하려면  
  
1. 빌드한 시각화 도우미가 들어 있는 DLL을 찾습니다.  
  
2. 이 DLL을 다음 위치 중 한 곳에 복사합니다.  
  
    - *VisualStudioInstallPath* `\Common7\Packages\Debugger\Visualizers`  
  
    - `My Documents\` *VisualStudioVersion* `\Visualizers`  
  
3. 원격 디버깅에 관리되는 시각화 도우미를 사용하려면 원격 컴퓨터의 동일한 경로에 DLL을 복사합니다.  
  
4. 디버깅 세션을 다시 시작합니다.  
  
## <a name="see-also"></a>참고 항목  
 [사용자 지정 시각화 도우미 만들기](../debugger/create-custom-visualizers-of-data.md)   
 [방법: 시각화 도우미 작성](../debugger/how-to-write-a-visualizer.md)

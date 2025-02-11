---
title: -Updateconfiguration (devenv.exe) | Microsoft 문서
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
helpviewer_keywords:
- /updateconfiguration Devenv switch
- Devenv, /updateconfiguration switch
- updateconfiguration Devenv switch
ms.assetid: 9a1084cc-8b68-4ccc-aaea-f95939164338
caps.latest.revision: 7
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 2f20463cd91148143a1d3fb7f7de5cc1649d683c
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65689344"
---
# <a name="updateconfiguration-devenvexe"></a>/Updateconfiguration (devenv.exe)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에 시스템의 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 패키지를 병합하고 MEF 캐시에서 변경 내용을 확인하도록 알립니다.  
  
## <a name="syntax"></a>구문  
  
```  
devenv /updateconfiguration  
```  
  
## <a name="remarks"></a>주의  
 VSIX 패키지를 설치하는 경우 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에서 이 명령을 자동으로 실행합니다. 파일을 패치한 후 `devenv.exe /updateconfiguration`을 실행하여 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에서 MEF 캐시를 업데이트하도록 해야 합니다. 이렇게 하면 수정 내용이 적합한지 여부를 평가할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 명령줄은 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)]에 시스템의 [!INCLUDE[vsprvs](../../includes/vsprvs-md.md)] 패키지를 병합하고 MEF 캐시에서 변경 내용을 확인하도록 합니다.  
  
```  
Devenv.exe /updateconfiguration  
```  
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio에서 개발 설정 사용자 지정](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)   
 [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)

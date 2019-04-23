---
title: VS 셸 배포 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
ms.assetid: be8f2ffe-a322-4ac0-9c9e-873bd28e5d5e
caps.latest.revision: 4
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6503efd0fa606042089e26b4cac23adcabdcb6e7
ms.sourcegitcommit: 1fc6ee928733e61a1f42782f832ead9f7946d00c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/22/2019
ms.locfileid: "60041018"
---
# <a name="vs-shell-deployment"></a>VS 셸 배포
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio를 확인할 수는 격리 된 셸 있습니다 도메인 특정 언어 및 해당 솔루션 표시 방법을 상호 작용 해야 하는 기능입니다. Visual Studio 격리 셸에 대 한 자세한 내용은 참조 하세요. [격리 셸 사용자 지정](../extensibility/customizing-the-isolated-shell.md)합니다. 격리 셸을 사용자 지정 하는 방법에 대 한 자세한 정보를 찾을 수 있습니다 [격리 셸 사용자 지정](http://msdn.microsoft.com/d75463cd-1155-42e4-8b7a-046ed6becbbf)합니다.  
  
### <a name="to-set-a-visual-studio-shell-as-the-deployment-target"></a>배포 대상으로 한 Visual Studio Shell을 설정 하려면  
  
1. 에 **DslPackage** 프로젝트를 열고 **source.extension.tt**합니다.  
  
2. 아래 `<SupportedProducts>` 삽입:  
  
    ```  
    <IsolatedShell Version="1.0">MyIsolatedShell</IsolatedShell>  
    ```  
  
     바꿉니다 *MyIsolatedShell* 격리 셸 패키지의 이름입니다.

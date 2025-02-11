---
title: 옵션 대화 상자, 프로젝트, Visual Basic 기본값 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ToolsOptionsPages.Projects.VBDefaults
helpviewer_keywords:
- Option Explicit statement, setting in the IDE
- Option Compare statement, setting in the IDE
- Option Strict statement, setting in the IDE
ms.assetid: 2465cd9d-18b6-4c4a-b1ea-86dbab23fc79
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: d49d593933475921a1edadf0ab1865d8cd15a16d
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65689283"
---
# <a name="visual-basic-defaults-projects-options-dialog-box"></a>옵션 대화 상자, 프로젝트, VB 기본값
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

Visual Basic 프로젝트 옵션에 대한 기본 설정을 지정합니다. 새 프로젝트를 만든 경우 지정된 옵션 문이 코드 편집기의 프로젝트 헤더에 추가됩니다. 이 옵션은 모든 Visual Basic 프로젝트에 적용됩니다.  
  
 이 대화 상자에 액세스하려면 **도구** 메뉴에서 **옵션**을 클릭하고 **프로젝트 및 솔루션**을 확장한 후 **VB 기본값**을 클릭합니다.  
  
 **Option Explicit**  
 변수의 명시적 선언이 필요하도록 컴파일러 기본값을 설정합니다. 기본적으로 **Option Explicit**은 **On**으로 설정됩니다. 자세한 내용은 [/optionexplicit](https://msdn.microsoft.com/library/5d296ab3-bafe-4c4d-9887-78f162ed86c7)을 참조하세요.  
  
 **Option Strict**  
 명시적 축소 변환이 필요하고 런타임에 바인딩이 허용되지 않도록 컴파일러 기본값을 설정합니다. 기본적으로 **Option Strict**은 **해제**로 설정됩니다. 자세한 내용은 [/optionstrict](https://msdn.microsoft.com/library/c7b10086-0fa4-49db-b3c8-4ae0db5957da)을 참조하세요.  
  
 **Option Compare**  
 문자열 비교를 위한 컴파일러 기본값을 이진(대/소문자 구분) 또는 텍스트(대/소문자 구분 안 함)로 설정합니다. 기본적으로 **Option Compare**는 **Binary**로 설정됩니다. 자세한 내용은 [/optioncompare](https://msdn.microsoft.com/library/7237b766-b44d-4cc5-9a3c-885348a7d9e4)를 참조하세요.  
  
 **Option Infer**  
 지역 형식 유추를 위한 컴파일러 기본값을 설정합니다. 기본적으로 새로 만든 프로젝트에 대해서는 **Option Infer**가 **설정**으로 설정되고 이전 버전의 Visual Basic에서 만든 마이그레이션된 프로젝트에 대해서는 **Off**로 설정됩니다. 자세한 내용은 [/optioninfer](https://msdn.microsoft.com/library/f6c09db1-0553-464a-abe3-d4510c61d6ed)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [솔루션 및 프로젝트](../../ide/solutions-and-projects-in-visual-studio.md)

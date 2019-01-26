---
title: 중첩 프로젝트 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- project nesting
- nested projects
- projects [Visual Studio SDK], child projects
- projects [Visual Studio SDK], nesting
ms.assetid: 12cce037-9840-4761-845e-5abd5fb317b0
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2ee02bbe830c8ef3eab5766cd97a4c04837dc585
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55014012"
---
# <a name="nesting-projects"></a>프로젝트 중첩
VS 패키지를 사용 하는 엔터프라이즈 응용 프로그램 개발자와 유사한 형식의 프로젝트에서 함께 그룹화 편리 하 게 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 사용 하 여 *중첩 프로젝트*합니다. 예를 들어, 엔터프라이즈 템플릿 프로젝트 범주로 그룹 프로젝트에 중첩 된 프로젝트를 사용합니다. 비즈니스 외관 프로젝트, 웹 UI 프로젝트의 경우 등에 하나의 범주에 함께 그룹화 됩니다.  
  
 이 시나리오의 경우 개발자는 각 부모 프로젝트 아래 중첩할 수는 프로젝트의 수에 제한이 없음을 개발자 한도 프로그래밍 방식으로 제공할 수 있지만 이 유형의 그룹도 만들 수 있습니다 재귀적 경우 자식 부모의 하위 항목인 자식의 하위 프로젝트를 아래 자식 프로젝트와 같은 형식의 프로젝트에 중첩 될 수 있습니다.  
  
 프로젝트 중첩 내장 속하지 않은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 중첩을 사용 하도록 설정 하 고 자식 프로젝트 내에서 중첩 하위 프로젝트 코드를 작성 해야 합니다. 부모 프로젝트에는 특수 VSPackage 또는 프로젝트 형식에 만들고 프로젝트 중첩을 구현 하는 데 필요한 코드를 포함 하는 고유한 GUID를 사용 하 여 등록입니다.  
  
 C# Example.Nested Project 예제에 중첩 된 프로젝트의 예제를 찾을 수 있습니다.  
  
## <a name="nested-projects-example"></a>중첩 된 프로젝트 예제  
 ![프로젝트 솔루션 중첩](../../extensibility/internals/media/vsnestedprojects.gif "vsNestedProjects")  
중첩 된 프로젝트 예제  
  
## <a name="see-also"></a>참고 항목  
 [방법: 중첩 된 프로젝트를 구현 합니다.](../../extensibility/internals/how-to-implement-nested-projects.md)   
 [중첩 된 프로젝트 언로드 및 다시 로드에 대 한 고려 사항](../../extensibility/internals/considerations-for-unloading-and-reloading-nested-projects.md)   
 [중첩 된 프로젝트에 대 한 마법사 지원](../../extensibility/internals/wizard-support-for-nested-projects.md)   
 [프로젝트 및 항목 템플릿 등록](../../extensibility/internals/registering-project-and-item-templates.md)   
 [중첩 된 프로젝트에 대 한 처리 명령 구현](../../extensibility/internals/implementing-command-handling-for-nested-projects.md)   
 [중첩 된 프로젝트에 대 한 항목 추가 대화 상자를 필터링](../../extensibility/internals/filtering-the-additem-dialog-box-for-nested-projects.md)   
 [검사 목록: 새 프로젝트 형식 만들기](../../extensibility/internals/checklist-creating-new-project-types.md)   
 [컨텍스트 매개 변수](../../extensibility/internals/context-parameters.md)   
 [마법사(.Vsz) 파일](../../extensibility/internals/wizard-dot-vsz-file.md)
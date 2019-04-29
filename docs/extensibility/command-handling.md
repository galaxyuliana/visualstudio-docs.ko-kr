---
title: 명령 처리 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - command handling
ms.assetid: 78f67d92-77f7-45cb-ad75-6e3346379cc3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1517410c58646bad2333db95b6f666937d890303
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62926912"
---
# <a name="command-handling"></a>명령 처리
편집기 새 명령을 정의할 수 있습니다. 명령은 상황에 맞는 메뉴 또는 도구 모음 메뉴에서 일반적으로 표시 됩니다.

 명령 및 메뉴를 정의 하는 방법에 대 한 자세한 내용은 참조 하세요. [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.

 어떤 상황에 맞는 메뉴를 차단 하 여 편집기에 표시 됩니다 언어 서비스를 제어할 수는 <xref:Microsoft.VisualStudio.VSConstants.VSStd2KCmdID> 열거형입니다. 또는 표식 당 기준 상황에 맞는 메뉴를 제어할 수 있습니다. 자세한 내용은 [언어 서비스 필터에 대 한 중요 명령](../extensibility/internals/important-commands-for-language-service-filters.md)입니다.

## <a name="add-commands-to-the-editor-context-menu"></a>편집기 상황에 맞는 메뉴에 명령 추가
 상황에 맞는 메뉴에 명령을 추가 하려면 먼저 특정 그룹에 속하는 메뉴 명령 집합을 정의 해야 합니다. 다음 예제에서 가져온 것은 *.vsct* 연습의 일환으로 생성 된 파일 [연습: 사용자 지정 편집기에 기능 추가](../extensibility/walkthrough-adding-features-to-a-custom-editor.md):

 \<Menu guid="guidCustomEditorCmdSet" id="IDMX_RTF" priority="0x0000" type="Context">

 \<Parent guid="guidCustomEditorCmdSet" id="0"/>

 \<Strings>

 \<ButtonText > CustomEditor 상황에 맞는 메뉴\</ButtonText >

 \<CommandName>CustomEditorContextMenu\</CommandName>

 \</Strings>

 \</Menu>

 \</Menus>

 텍스트를 사용 하 여 상황에 맞는 메뉴 명령을 추가 하는 위의 텍스트가 **CustomEditor 상황에 맞는 메뉴**합니다. 메뉴 GUID에는이 편집기를 사용 하 여 만든 명령 집합의 일부입니다. 유형 "컨텍스트"입니다.

 정의 하지 않아도 되는 미리 정의 된 명령을 사용할 수도 있습니다는 *.vsct* 파일입니다. 예를 들어 검토 합니다 *EditorPane.cs* Visual Studio 패키지 템플릿에 의해 생성 된 파일입니다. 볼 수 있습니다는 미리 정의 된 명령 집합을 같은 <xref:Microsoft.VisualStudio.VSConstants.VSStd97CmdID> 정의한 <xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>와 같은 명령 처리기에서 처리 되는 `onSelectAll` 메서드.

## <a name="see-also"></a>참고자료
- [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)
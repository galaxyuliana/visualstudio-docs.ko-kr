---
title: 코드 스타일 기본 설정
ms.date: 03/10/2017
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
f1_keywords:
- VS.ToolsOptionsPages.Text_Editor.CSharp.Code_Style.General
- VS.ToolsOptionsPages.Text_Editor.Basic.Code_Style.General
ms.workload:
- multiple
ms.openlocfilehash: f33c1edec4b4093e9157a59618befa2e1175be49
ms.sourcegitcommit: e3d96b20381916bf4772f9db52b22275763bb603
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/31/2019
ms.locfileid: "55483993"
---
# <a name="code-style-preferences"></a>코드 스타일 기본 설정

**도구** 메뉴에서 **옵션** 대화 상자를 열어 C# 및 Visual Basic 프로젝트에 대한 코드 스타일 기본 설정을 설정할 수 있습니다. **옵션** 대화 상자에서 **텍스트 편집기** > [**C#** 또는 **기본**] > **코드 스타일**  >  **일반**을 선택합니다. 이 창에서 설정한 옵션은 로컬 머신에만 적용됩니다.

목록의 각 항목에는 선택한 기본 설정의 미리 보기가 표시됩니다.

![코드 스타일 옵션](media/code-style-quick-actions-dialog.png)

> [!NOTE]
> 이 토픽은 Windows의 Visual Studio에 적용됩니다. Mac용 Visual Studio는 [Mac용 Visual Studio의 편집기 동작](/visualstudio/mac/editor-behavior)을 참조하세요.

## <a name="preference-and-severity"></a>기본 설정 및 심각도

각 항목에 대해 각 줄에 있는 드롭다운을 사용하여 **기본 설정** 및 **심각도** 값을 설정할 수 있습니다. 심각도는 **없음**, **제안**, **경고** 또는 **오류**로 설정할 수 있습니다. 코드 스타일에 대해 [빠른 작업](../ide/quick-actions.md)을 사용하려면 **심각도** 설정이 **없음** 이외의 값으로 설정되어 있는지 확인합니다. 선호하지 않는 스타일이 사용될 경우 **빠른 작업** 전구 ![전구](media/vs2015_lightbulbsmall.png), 오류 전구 ![오류 전구](media/error-bulb.png) 또는 스크루드라이버 ![스크루드라이버](media/screwdriver.png) 아이콘이 표시되고, **빠른 작업** 목록에서 옵션을 선택하면 코드를 원하는 스타일로 자동으로 다시 작성할 수 있습니다.

## <a name="editorconfig-files"></a>EditorConfig 파일

또한 .NET에 대한 코드 스타일 설정은 [EditorConfig](../ide/editorconfig-code-style-settings-reference.md) 파일을 사용하여 관리할 수 있습니다. EditorConfig 파일의 설정은 **옵션** 대화 상자에서 선택한 옵션보다 우선합니다. EditorConfig 파일을 사용하여 전체 리포지토리 또는 프로젝트에 코딩 스타일을 적용하고 구성할 수 있습니다.

## <a name="format-document-command"></a>문서 서식 명령

Visual Studio 2017 버전 15.8 이상에서는 파일에서 usings을 제거하고 정렬하거나 코드 스타일 기본 설정을 적용하는 등 추가 코드 정리를 수행하도록 **문서 서식** 명령(**편집** > **고급** > **문서 서식**)을 구성할 수 있습니다. [서식 지정 옵션 페이지](reference/options-text-editor-csharp-formatting.md#format-document-settings)에 적용하려는 **문서 서식**의 설정을 정의할 수 있습니다.

코드 정리는 *.editorconfig* 파일에 구성된 설정 또는 **도구** > **옵션** > **텍스트 편집기** > **C#** > [**코드 스타일** 또는 **서식 지정**]에서 설정된 해당 규칙이나 파일의 결함을 고려합니다.

Visual Studio 2017에서 처음으로 **문서 서식** 명령을 트리거하면 노란색 정보 표시줄에서는 코드 정리 설정을 구성하라는 메시지를 표시합니다.

> [!TIP]
> *.editorconfig* 파일에서 **없음**으로 구성된 규칙은 코드 정리에 참여하지 않지만 **빠른 작업 및 리팩터링** 메뉴를 통해 개별적으로 적용될 수 있습니다.

## <a name="see-also"></a>참고 항목

- [빠른 작업](../ide/quick-actions.md)
- [EditorConfig에 대한 .NET 코딩 규칙 설정](../ide/editorconfig-code-style-settings-reference.md)
- [편집기 동작(Mac용 Visual Studio)](/visualstudio/mac/editor-behavior)
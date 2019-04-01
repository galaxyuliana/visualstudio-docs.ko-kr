---
title: .NET Framework 버전 대상
ms.date: 03/21/2019
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- .NET Framework version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: ba8bdcade321c3660e89ab6b7cf6e0b79471b393
ms.sourcegitcommit: 3201da3499051768ab59f492699a9049cbc5c3c6
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2019
ms.locfileid: "58355398"
---
# <a name="how-to-target-a-version-of-the-net-framework"></a>방법: 한 버전의 .NET Framework를 대상으로 지정

이 문서에서는 프로젝트를 만들 때 .NET Framework 버전을 대상으로 하는 방법을 설명합니다. 기존 Visual Basic, C# 또는 F# 프로젝트에서 대상 버전을 변경하는 방법도 설명합니다.

> [!IMPORTANT]
> C++ 프로젝트용 대상 버전을 변경하는 방법에 대한 자세한 내용은 [방법: 대상 프레임워크 및 플랫폼 도구 세트 수정](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)을 참조하세요.

## <a name="target-a-version-when-you-create-a-project"></a>프로젝트를 만들 때 버전 대상 지정

프로젝트를 만들 때 사용 가능한 .NET Framework 버전은 설치된 버전과 선택한 프로젝트 템플릿에 따라 달라집니다.

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. 만들려는 프로젝트의 형식에 대한 템플릿을 선택합니다. 프로젝트의 이름을 입력합니다.

1. 대화 상자의 맨 아래에 있는 **Framework** 드롭다운 목록에서 프로젝트를 대상으로 지정할 .NET Framework 버전을 선택합니다.

   프레임워크 목록에는 사용자가 선택한 템플릿에 적용 가능한 버전만 표시됩니다. .NET Core와 같은 일부 프로젝트 형식에는 .NET Framework가 필요하지 않습니다. 이러한 경우 **Framework** 드롭다운 목록이 숨겨집니다.

   ::: moniker range="vs-2017"

   ![새 프로젝트 대화 상자의 Framework 드롭다운](media/vside-newproject-framework.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![VS 2019의 Framework 선택기](media/vs-2019/configure-new-project-framework.png)

   ::: moniker-end

1. [프로젝트 만들기](create-new-project.md)를 계속 진행합니다.

## <a name="change-the-targeted-version"></a>대상 버전 변경

이 절차를 수행하여 Visual Basic, C# 또는 F# 프로젝트에서 .NET Framework의 대상 버전을 변경할 수 있습니다.

1. **솔루션 탐색기**에서 변경하려는 프로젝트의 바로 가기 메뉴를 연 후 **속성**을 선택합니다.

    ![Visual Studio 솔루션 탐색기 속성](../ide/media/vs_slnexplorer_properties.png)

1. **속성** 창의 왼쪽 열에서 **애플리케이션** 탭을 선택합니다.

    ![Visual Studio 응용 프로그램 속성 응용 프로그램 탭](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > UWP 앱을 만든 후에는 Windows 또는 .NET Framework의 대상 버전을 변경할 수 없습니다.

1. **대상 프레임워크** 목록에서 원하는 버전을 선택합니다.

1. [확인] 대화 상자가 나타나면 **예** 단추를 선택합니다.

    프로젝트가 언로드됩니다. 다시 로드되면 이 프로젝트는 방금 선택한 .NET Framework 버전을 대상으로 지정합니다.

    > [!NOTE]
    > 코드에 사용자가 대상으로 지정한 것과 다른 버전의 .NET Framework에 대한 참조가 포함된 경우, 코드를 컴파일하거나 실행할 때 오류 메시지가 나타날 수 있습니다. 이러한 오류를 해결하려면 참조를 수정해야 합니다. [.NET Framework 대상 지정 오류 문제 해결](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Visual Studio 멀티 타기팅 개요](../ide/visual-studio-multi-targeting-overview.md)
- [.NET Framework 대상 지정 오류 문제 해결](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [애플리케이션 페이지, 프로젝트 디자이너(C#)](../ide/reference/application-page-project-designer-csharp.md)
- [애플리케이션 페이지, 프로젝트 디자이너(Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [방법: 대상 프레임워크 및 플랫폼 도구 세트 수정(C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)
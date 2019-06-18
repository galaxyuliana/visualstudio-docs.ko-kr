---
title: .NET 버전 대상 지정
ms.date: 03/21/2019
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET [Visual Studio]
- .NET version [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 2c316610fc007e3e8642567c01a5172feb461bda
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747130"
---
# <a name="how-to-target-a-version-of-net"></a>방법: .NET 버전 대상 지정

이 문서에서는 .NET Framework 프로젝트를 만들 때 특정 버전의 .NET Framework를 대상으로 하는 방법을 설명합니다. 기존 Visual Basic, C# 또는 F# 프로젝트에서 대상 버전을 변경하는 방법도 설명합니다.

> [!IMPORTANT]
> C++ 프로젝트용 대상 버전을 변경하는 방법에 대한 자세한 내용은 [방법: 대상 프레임워크 및 플랫폼 도구 세트 수정](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)을 참조하세요.

## <a name="target-a-version-when-you-create-a-project"></a>프로젝트를 만들 때 버전 대상 지정

.NET Framework 프로젝트를 만들 때 사용 가능한 .NET Framework 버전은 설치된 버전과 선택한 프로젝트 템플릿에 따라 달라집니다.

1. 메뉴 모음에서 **파일** > **새로 만들기** > **프로젝트**를 선택합니다.

1. 만들려는 프로젝트의 형식에 대한 .NET Framework 템플릿을 선택합니다.

1. 대화 상자의 맨 아래에 있는 **Framework** 드롭다운 목록에서 프로젝트를 대상으로 지정할 .NET Framework 버전을 선택합니다.

   프레임워크 목록에는 사용자가 선택한 템플릿에 적용 가능한 버전만 표시됩니다.

   > [!NOTE]
   > .NET Core와 같은 일부 프로젝트 형식에는 **Framework**가 필요하지 않습니다.

   ::: moniker range="vs-2017"

   ![Visual Studio 2017 새 프로젝트 대화 상자의 Framework 드롭다운](media/vside-newproject-framework.png)

   ::: moniker-end

   ::: moniker range=">=vs-2019"

   ![VS 2019의 Framework 선택기](media/vs-2019/configure-new-project-framework.png)

   ::: moniker-end

1. [프로젝트 만들기](create-new-project.md)를 계속 진행합니다.

## <a name="change-the-targeted-version"></a>대상 버전 변경

이 절차를 수행하여 Visual Basic, C# 또는 F# 프로젝트에서 .NET의 대상 버전을 변경할 수 있습니다.

1. **솔루션 탐색기**에서 변경하려는 프로젝트의 바로 가기 메뉴를 연 후 **속성**을 선택합니다.

    ![Visual Studio 솔루션 탐색기 속성](../ide/media/vs_slnexplorer_properties.png)

1. **속성** 창의 왼쪽 열에서 **애플리케이션** 탭을 선택합니다.

    ![Visual Studio 응용 프로그램 속성 응용 프로그램 탭](../ide/media/vs_slnexplorer_properties_applicationtab.png)

    > [!NOTE]
    > UWP 앱을 만든 후에는 Windows 또는 .NET의 대상 버전을 변경할 수 없습니다.

1. **대상 프레임워크** 목록에서 원하는 버전을 선택합니다.

1. [확인] 대화 상자가 나타나면 **예** 단추를 선택합니다.

    프로젝트가 언로드됩니다. 다시 로드되면 이 프로젝트는 방금 선택한 .NET 버전을 대상으로 지정합니다.

    > [!NOTE]
    > 코드에 사용자가 대상으로 지정한 것과 다른 버전의 .NET에 대한 참조가 포함된 경우, 코드를 컴파일하거나 실행할 때 오류 메시지가 나타날 수 있습니다. 이러한 오류를 해결하려면 참조를 수정해야 합니다. [.NET 대상 지정 오류 문제 해결](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [Framework 대상 지정 개요](../ide/visual-studio-multi-targeting-overview.md)
- [.NET Framework 대상 지정 오류 문제 해결](../msbuild/troubleshooting-dotnet-framework-targeting-errors.md)
- [애플리케이션 페이지, 프로젝트 디자이너(C#)](../ide/reference/application-page-project-designer-csharp.md)
- [애플리케이션 페이지, 프로젝트 디자이너(Visual Basic)](../ide/reference/application-page-project-designer-visual-basic.md)
- [방법: 대상 프레임워크 및 플랫폼 도구 세트 수정(C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)
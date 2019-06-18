---
title: 대상 .NET Framework
ms.date: 02/06/2018
ms.topic: conceptual
helpviewer_keywords:
- targeting .NET Framework [Visual Studio]
- framework targeting [Visual Studio]
- .NET framework targeting [Visual Studio]
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: cb7af190ac7fc5d4d5ce547029689f6c902a6e4f
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747635"
---
# <a name="framework-targeting-overview"></a>Framework 대상 지정 개요

Visual Studio에서는 프로젝트에서 대상으로 하려는 .NET의 버전을 지정할 수 있습니다. .NET Framework 앱이 다른 컴퓨터에서 실행되려면 애플리케이션이 대상으로 하는 Framework 버전이 컴퓨터에 설치된 Framework 버전과 호환되어야 합니다.

대상 프레임워크에 대한 자세한 내용은 [대상 프레임워크](/dotnet/standard/frameworks)를 참조하세요.

여러 가지 버전의 .NET를 대상으로 지정하는 프로젝트가 포함된 솔루션을 만들 수도 있습니다. 프레임워크 대상 지정을 통해 애플리케이션에서 지정된 프레임워크 버전에서 제공되는 기능만 사용하도록 할 수 있습니다.

> [!TIP]
> 다른 플랫폼에 대한 애플리케이션을 대상으로 지정할 수도 있습니다. 자세한 내용은 [멀티 타기팅](../msbuild/msbuild-multitargeting-overview.md)을 참조하세요.

## <a name="framework-targeting-features"></a>프레임워크 대상 지정 기능

프레임워크 대상 지정에는 다음 기능이 포함됩니다.

- 이전 버전의 프레임워크를 대상으로 하는 프로젝트를 열면 Visual Studio에서 프로젝트를 자동으로 업그레이드하거나 대상을 있는 그대로 유지할 수 있습니다.

- .NET Framework 프로젝트를 만들 때 대상으로 지정할 .NET Framework의 버전을 지정할 수 있습니다.

- 단일 프로젝트에서 [여러 프레임워크를 대상 지정](/dotnet/standard/frameworks#how-to-specify-target-frameworks)할 수 있습니다.

- 같은 솔루션에 포함된 여러 프로젝트에서 각각 .NET의 다른 버전을 대상으로 지정할 수 있습니다.

- 기존 프로젝트에서 대상으로 지정하는 .NET의 버전을 변경할 수 있습니다.

   프로젝트가 대상으로 하는 .NET의 버전을 변경하면 Visual Studio에서는 필요에 따라 참조 및 구성 파일을 변경합니다.

이전 프레임워크 버전을 대상으로 지정하는 프로젝트 관련 작업을 할 경우 Visual Studio에서는 다음과 같이 개발 환경을 동적으로 변경합니다.

- **새 항목 추가** 대화 상자, **새 참조 추가** 대화 상자 및 **서비스 참조 추가** 대화 상자에서 항목을 필터링하여 대상 버전에서 사용할 수 없는 선택 항목을 생략합니다.

- **도구 상자**에서 사용자 지정 컨트롤을 필터링하여 대상 버전에서 사용할 수 없는 컨트롤을 제거하고 여러 컨트롤을 사용할 수 있을 경우에는 가장 최신 컨트롤만 표시합니다.

- **IntelliSense**를 필터링하여 대상 버전에서 사용할 수 없는 언어 기능을 생략합니다.

- **속성** 창에서 속성을 필터링하여 대상 버전에서 사용할 수 없는 속성을 생략합니다.

- 메뉴 옵션을 필터링하여 대상 버전에서 사용할 수 없는 옵션을 생략합니다.

- 빌드에는 컴파일러 버전 및 대상 버전에 적절한 컴파일러 옵션을 사용합니다.

> [!NOTE]
> - 프레임워크 대상 지정을 수행해도 애플리케이션이 제대로 실행되지 않을 수 있습니다. 애플리케이션을 테스트하여 대상 버전에 대해 실행되는지 확인해야 합니다.
> - .NET Framework 2.0 이하의 프레임워크 버전은 대상으로 지정할 수 없습니다.

## <a name="select-a-target-framework-version"></a>대상 프레임워크 버전 선택

.NET Framework 프로젝트를 만들 때 프로젝트 템플릿을 선택한 후 대상 .NET Framework 버전을 선택할 수 있습니다. 사용 가능한 프레임워크 목록에는 선택한 템플릿 유형에 적용 가능한 설치된 프레임워크 버전이 포함됩니다. 비 .NET Framework 프로젝트 템플릿의 경우(예: .NET Core 템플릿), **Framework** 드롭다운 목록이 나타나지 않습니다.

::: moniker range="vs-2017"

![VS 2017의 프레임워크 드롭다운](media/vside-newproject-framework.png)

::: moniker-end

::: moniker range=">=vs-2019"

![VS 2019의 프레임워크 드롭다운](media/vs-2019/configure-new-project-framework.png)

::: moniker-end

기존 프로젝트의 경우 프로젝트 속성 대화 상자에서 대상 .NET 버전을 변경할 수 있습니다. 자세한 내용은 [방법: .NET 버전 대상 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)

## <a name="resolve-system-and-user-assembly-references"></a>시스템 및 사용자 어셈블리 참조 확인

.NET 버전을 대상으로 지정하려면 먼저 적절한 어셈블리 참조를 설치해야 합니다. [.NET 다운로드](https://www.microsoft.com/net/download/windows) 페이지에서 다양한 버전의 .NET 개발자 팩을 다운로드할 수 있습니다.

.NET Framework 프로젝트의 경우 **참조 추가** 대화 상자에서는 실수로 프로젝트에 추가될 수 없도록 대상 .NET Framework 버전과 관련이 없는 시스템 어셈블리를 비활성화합니다. (시스템 어셈블리는 .NET Framework 버전에 포함된 *.dll* 파일입니다.) 대상 버전 이상의 프레임워크 버전에 속한 참조는 확인되지 않고 이런 참조에 따라 결정되는 컨트롤을 추가할 수 없습니다. 해당 참조를 사용하도록 설정하려면 프로젝트의 .NET Framework 대상을 참조가 포함된 대상으로 다시 설정합니다. 자세한 내용은 [방법: 프레임워크 버전 대상 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하세요.

어셈블리 참조에 대한 자세한 내용은 [디자인 타임에 어셈블리 확인](../msbuild/resolving-assemblies-at-design-time.md)을 참조하세요.

## <a name="enable-linq"></a>LINQ 사용

.NET Framework 3.5 이상을 대상으로 지정하면 **System.Core**에 대한 참조 및 <xref:System.Linq>에 대한 프로젝트 수준 가져오기(Visual Basic에서만)가 자동으로 추가됩니다. LINQ 기능을 사용하려면 `Option Infer`도 켜야 합니다(Visual Basic에서만). 대상을 이전 .NET Framework 버전으로 변경하면 참조 및 가져오기가 자동으로 제거됩니다. 자세한 내용은 [LINQ 작업](/dotnet/csharp/tutorials/working-with-linq)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [대상 프레임워크](/dotnet/standard/frameworks)
- [멀티 타기팅(MSBuild)](../msbuild/msbuild-multitargeting-overview.md)
- [방법: 대상 프레임워크 및 플랫폼 도구 세트 수정(C++)](/cpp/build/how-to-modify-the-target-framework-and-platform-toolset)
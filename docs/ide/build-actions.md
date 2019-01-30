---
title: 파일에 대한 빌드 작업
ms.date: 11/19/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-compile
ms.topic: reference
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 45a0e4822bc9b6d20bd2cf63d664e6cba97c77bf
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54951302"
---
# <a name="build-actions"></a>빌드 작업

Visual Studio 프로젝트의 모든 파일에는 빌드 작업이 있습니다. 빌드 작업은 프로젝트가 컴파일될 때 파일에 발생하는 작업을 제어합니다.

> [!NOTE]
> 이 토픽은 Windows의 Visual Studio에 적용됩니다. Mac용 Visual Studio의 경우 [Mac용 Visual Studio에서 빌드 작업](/visualstudio/mac/build-actions)을 참조하세요.

## <a name="set-a-build-action"></a>빌드 작업 설정

파일에 대한 빌드 작업을 설정하려면 **솔루션 탐색기**에서 파일을 선택하고 **Alt**+**Enter**를 눌러 **속성** 창에서 파일의 속성을 엽니다. 또는 **솔루션 탐색기**에서 파일을 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다. **속성** 창의 **고급** 섹션 아래에 있는 **빌드 작업** 옆의 드롭다운 목록을 사용하여 파일에 대한 빌드 작업을 설정합니다.

![Visual Studio에서 파일에 대한 작업 빌드](media/build-actions.png)

## <a name="build-action-values"></a>빌드 작업 값

C# 및 Visual Basic 프로젝트 파일에 대한 빌드 작업 중 일부는 다음과 같습니다.

* **없음** - 파일은 어떤 방식으로든 빌드에 일부가 아닙니다. 이 값은 예를 들어 "ReadMe" 파일과 같은 문서 파일에 사용할 수 있습니다.
* **컴파일** - 파일이 컴파일러에 소스 파일로 전달됩니다.
* **콘텐츠** - **콘텐츠**로 표시된 파일은 <xref:System.Windows.Application.GetContentStream%2A?displayProperty=nameWithType>을 호출하여 스트림으로 검색할 수 있습니다. ASP.NET 프로젝트의 경우 이러한 파일은 배포 시 사이트의 일부로 포함됩니다.
* **포함 리소스** - 파일이 어셈블리에 포함될 리소스로 컴파일러에 전달됩니다. <xref:System.Reflection.Assembly.GetManifestResourceStream%2A?displayProperty=fullName>을 호출하여 어셈블리에서 파일을 읽을 수 있습니다.
* **AdditionalFiles** - 입력으로 C# 또는 Visual Basic 컴파일러에 전달되는 비소스 텍스트 파일입니다. 이 빌드 작업은 주로 코드 품질을 확인하기 위해 프로젝트에서 참조되는 [분석기](../code-quality/roslyn-analyzers-overview.md)에 입력을 제공하는 데 사용됩니다. 자세한 내용은 [추가 파일 사용](https://github.com/dotnet/roslyn/blob/master/docs/analyzers/Using%20Additional%20Files.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [C# 컴파일러 옵션](/dotnet/csharp/language-reference/compiler-options/listed-alphabetically)
- [Visual Basic 컴파일러 옵션](/dotnet/visual-basic/reference/command-line-compiler/compiler-options-listed-alphabetically)
- [빌드 작업(Mac용 Visual Studio)](/visualstudio/mac/build-actions)
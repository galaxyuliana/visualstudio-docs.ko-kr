---
title: Hello World 확장 자습서 | Microsoft Docs
ms.date: 07/10/2017
ms.topic: conceptual
ms.assetid: f74e1ad1-1ee5-4360-9bd5-d82467b884ca
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: f354b31e3979aacdb55aba566a646616ddc4108e
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56688344"
---
# <a name="create-your-first-extension-hello-world"></a>첫 번째 확장을 만듭니다. Hello World

이 Hello World 예제에서는 Visual Studio에 대 한 첫 번째 확장 프로그램을 만드는 과정 안내 합니다. 이 자습서에서는 Visual Studio에 새 명령을 추가 하는 방법을 보여 줍니다.

프로세스에서 학습할 방법:

* **[확장성 프로젝트 만들기](#create-an-extensibility-project)**
* **[사용자 지정 명령 추가](#add-a-custom-command)**
* **[소스 코드를 수정 합니다.](#modify-the-source-code)**
* **[실행](#run-it)**

예를 들어 사용할지 Visual C# 사용자 지정 메뉴 단추를 "Hello World 예를 들어!" 라는 추가 하려면 다음과 같습니다.

![Hello World 명령](media/hello-world-say-hello-world.png)

> [!NOTE]
> 이 문서에서는 Windows에서 Visual Studio에 적용 됩니다. Mac 용 Visual Studio에 대 한 참조 [Mac 용 Visual Studio 확장 연습](/visualstudio/mac/extending-visual-studio-mac-walkthrough)합니다.

## <a name="prerequisites"></a>전제 조건

시작 하기 전에 설치 했는지 확인 합니다 **Visual Studio 확장 개발** VSIX 템플릿에 필요 하 고 샘플 코드를 포함 하는 작업입니다.

> [!NOTE]
> (Community, Professional 또는 Enterprise) Visual Studio 확장성 프로젝트를 만들려면 Visual Studio의 모든 버전을 사용할 수 있습니다.

## <a name="create-an-extensibility-project"></a>확장성 프로젝트 만들기

1단계. **파일** 메뉴에서 클릭 **새 프로젝트**합니다. 화면 아래쪽에서 프로젝트의 이름을 입력 합니다.

2단계. **템플릿** 메뉴에서 클릭 **Visual C#**, 클릭 **확장성**를 클릭 하 고 **VSIX 프로젝트**합니다.

![새 프로젝트](media/hello-world-new-project.png)

이제 시작 페이지 및 일부 샘플 리소스 표시 됩니다.

::: moniker range="vs-2017"

이 자습서를 두고 돌아올 것 해야 할 경우에서 새 HelloWorld 프로젝트를 찾을 수 있습니다 합니다 **시작 페이지** 에 **최근** 섹션입니다.

::: moniker-end

## <a name="add-a-custom-command"></a>사용자 지정 명령 추가

1단계. 매니페스트를 선택 하면 인스턴스, 메타 데이터, 설명 및 버전에 대 한 변경할 수 있는 옵션을 볼 수 있습니다.

2단계. 프로젝트 (솔루션 아님)를 마우스 오른쪽 단추로 클릭 합니다. 상황에 맞는 메뉴를 클릭 **추가**를 클릭 하 고 **새 항목**합니다.

3단계. 선택 된 **확장성** 섹션을 클릭 한 다음 **사용자 지정 명령**입니다.

4단계. 에 **이름을** 맨 아래에 필드에 이름을, 예를 들어 *Command.cs*합니다.

![사용자 지정 명령](media/hello-world-custom-command.png)

새 명령에 포함 된 **솔루션 탐색기** 아래의 합니다 **리소스** 분기 합니다. 또한 이것이 PNG와 ICO 파일 이미지를 수정 하려는 경우와 같은 명령에 관련 된 다른 파일을 찾을 수 있습니다.

## <a name="modify-the-source-code"></a>소스 코드를 수정 합니다.

이 시점에서 추가 하는 단추는 상당히 제네릭입니다. 변경 하려는 경우 VSCT 파일 및 CS 파일을 수정 해야 합니다.

* VSCT 파일은 여기서 있습니다 수 명령을, 이름 바꾸기 뿐만 어디에서 Visual Studio 명령 시스템을 정의 합니다. VSCT 파일을 살펴보면서 코드 컨트롤의 각 섹션을 설명 하는 주석 처리 된 코드를 많이 확인할 수 있습니다.

* CS 파일이 있는 click 처리기 등의 작업을 정의할 수 있습니다.

1단계. **솔루션 탐색기**, 새 명령에 대 한 VSCT 파일을 찾습니다. 이 경우 호출 하는 *CommandPackage.vsct*합니다.

![명령은 패키지 vsct](media/hello-world-command-package-vsct.png)

2단계. 변경 된 `ButtonText` 매개 변수를 `Say Hello World!`입니다.

```xml
  ...
  <Button guid="guidCommandPackageCmdSet" id="CommandId" priority="0x0100" type="Button">
     <Parent guid="guidCommandPackageCmdSet" id="MyMenuGroup" />
     <Icon guid="guidImages" id="bmpPic1" />
     <Strings>
        <ButtonText>Say Hello World!</ButtonText>
     </Strings>
  </Button>
  ...
```

3단계. 로 돌아가서 **솔루션 탐색기** 찾고 합니다 *Command.cs* 파일입니다. 문자열을 변경 `message` 명령에 대해 `string.Format(..)` 에 `Hello World!`입니다.

```csharp
  ...
  private void MenuItemCallback(object sender, EventArgs e)
  {
    string message = "Hello World!";
    string title = "Command1";

    // Show a message box to prove we were here
    VsShellUtilities.ShowMessageBox(
        this.ServiceProvider,
        message,
        title,
        OLEMSGICON.OLEMSGICON_INFO,
        OLEMSGBUTTON.OLEMSGBUTTON_OK,
        OLEMSGDEFBUTTON.OLEMSGDEFBUTTON_FIRST);
  }
  ...
```

각 파일에 변경 내용을 저장 해야 합니다.

## <a name="run-it"></a>실행

이제 Visual Studio 실험적 인스턴스에서 소스 코드를 실행할 수 있습니다.

1단계. 클릭 **시작** 도구 모음에서 합니다. 이 프로젝트를 빌드하고 라는 Visual Studio의 새 인스턴스를 시작 하 고 디버거를 시작 합니다 **실험적 인스턴스**합니다.

단어를 보면 **실험적 인스턴스** Visual Studio 제목 표시줄에 있습니다.

![실험적 인스턴스에서 제목 표시줄](media/hello-world-exp-instance.png)

2단계. 에 **도구** 메뉴의 **실험적 인스턴스**, 클릭 **Say Hello World!**.

![최종 결과](media/hello-world-final-result.png)

새 사용자 지정 명령에서 출력을 표시,이 경우 화면의 가운데에 대화 상자 제공 하는 **Hello World!** 반환됩니다.

## <a name="next-steps"></a>다음 단계

Visual Studio 확장성을 사용 하는 기본 사항을 배웠으므로 다음과 같습니다. 여기서 자세히 알아볼 수 있습니다

* [Visual Studio 확장 개발을 시작할](starting-to-develop-visual-studio-extensions.md) -샘플, 자습서입니다. 확장 프로그램을 게시 하 고
* [Visual Studio 2017 SDK의 새로운 기능](what-s-new-in-the-visual-studio-2017-sdk.md) -Visual Studio 2017의 새로운 확장성 기능
* [Visual Studio SDK 내에서](internals/inside-the-visual-studio-sdk.md) -Visual Studio 확장성의 세부 정보에 알아봅니다.
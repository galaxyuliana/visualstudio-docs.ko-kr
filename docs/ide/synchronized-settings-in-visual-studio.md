---
title: 설정 동기화
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
ms.assetid: a3d2ea29-be5d-4012-9820-44b06adbb7dd
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 989b658f359e8ce47b9b5bdb2c76892463433aa7
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/26/2019
ms.locfileid: "55070971"
---
# <a name="synchronize-visual-studio-settings-across-multiple-computers"></a>여러 컴퓨터에서 Visual Studio 설정 동기화

동일한 개인 설정 계정을 사용하여 여러 컴퓨터에서 Visual Studio에 로그인하는 경우 설정이 컴퓨터에서 동기화될 수 있습니다.

## <a name="synchronized-settings"></a>동기화된 설정

기본적으로 다음 설정이 동기화됩니다.

- 개발 설정입니다. Visual Studio를 처음 열 때 설정 컬렉션을 선택하지만 언제든지 선택 항목을 변경할 수 있습니다. 자세한 내용은 [환경 설정](../ide/environment-settings.md)을 참조하세요.

- 사용자 정의 명령 별칭. 명령 별칭을 정의하는 방법에 대한 자세한 내용은 [Visual Studio 명령 별칭](../ide/reference/visual-studio-command-aliases.md)을 참조하세요.

- **창** > **창 레이아웃 관리** 페이지의 사용자 정의 창 레이아웃입니다.

- **도구** > **옵션** 페이지의 다음 옵션:

   - **환경** > **일반** 옵션 페이지의 테마 및 메뉴 모음 대/소문자 설정입니다.

   - **환경** > **글꼴 및 색** 옵션 페이지의 모든 설정입니다.

   - **환경** > **키보드** 옵션 페이지의 모든 바로 가기 키입니다.

   - **환경** > **탭 및 창** 옵션 페이지의 모든 설정입니다.

   - **환경** > **시작** 옵션 페이지의 모든 설정입니다.

   - **텍스트 편집기** 옵션 페이지의 모든 설정입니다.

   - **XAML 디자이너**의 옵션 페이지의 모든 설정입니다.

## <a name="turn-off-synchronized-settings-on-a-particular-computer"></a>특정 컴퓨터에서 동기화된 설정 끄기

Visual Studio의 동기화된 설정이 기본적으로 켜져 있습니다. **도구** > **옵션** > **환경** > **계정** 페이지로 이동하고 **Visual Studio에 로그인할 때 디바이스에서 설정 동기화** 선택을 취소하면 컴퓨터에서 동기화된 설정을 끌 수 있습니다.

예를 들어 컴퓨터 “A”에서 Visual Studio의 설정을 동기화하지 않기로 결정하면 컴퓨터 “A”에서 수행한 변경 사항이 컴퓨터 “B”나 컴퓨터 “C”에 나타나지 않습니다. 컴퓨터 “B”와 “C”는 계속 서로 동기화되지만 컴퓨터 “A”와는 동기화되지 않습니다.

> [!NOTE]
> **도구** > **옵션** > **환경** > **계정** 페이지에서 옵션을 선택 취소하여 설정을 동기화하지 않도록 선택한 경우, 동일한 컴퓨터에 있는 Visual Studio의 다른 버전이나 에디션에는 영향을 미치지 않습니다. Visual Studio의 이러한 side-by-side 설치는 해당 설정을 계속 동기화합니다(여기에서 옵션을 선택 취소하지 않는 경우).

## <a name="synchronize-settings-across-visual-studio-family-products-and-editions"></a>Visual Studio 제품군 제품 및 버전 간에 설정 동기화

설정은 *side-by-side*로 설치된 Visual Studio 버전과 에디션 간에 동기화됩니다. Blend for Visual Studio를 포함한 Visual Studio 제품군 제품 간에서도 설정이 동기화됩니다. 그러나 개별 제품군 제품에는 Visual Studio와 공유되지 않는 자체 설정이 있을 수 있습니다. 예를 들어 컴퓨터 "A"의 Blend for Visual Studio에 관련된 설정은 컴퓨터 "A" 또는 "B"의 Visual Studio와 공유되지 않습니다.

## <a name="side-by-side-synchronized-settings"></a>Side-by-Side 동기화된 설정

Visual Studio 2017 버전 15.3 이상에서 도구 창 레이아웃 같은 특정 설정이 Visual Studio 2017의 병렬 설치 간에 공유되지 않습니다. *%userprofile%\Documents\Visual Studio 2017\Settings*에서 *currentsettings.vssettings* 파일은 *%localappdata%\ Microsoft\VisualStudio\15.0_xxxxxxxx\Settings*와 비슷한 설치 관련 폴더에 있습니다.

> [!NOTE]
> 새로운 설치 관련 설정을 사용하려면 새로 설치합니다. 기존 Visual Studio 2017 설치를 현재 업데이트로 업그레이드하는 경우 기존 공유 위치를 사용합니다.

현재 Visual Studio 2017의 side-by-Side 설치가 있는 경우 새 설치 관련 설정 파일 위치를 사용하려면 다음 단계를 수행하세요.

1. Visual Studio 2017 버전 15.3 이상으로 업그레이드합니다.

1. **설정 가져오기\내보내기** 마법사를 사용하여 모든 기존 설정을 *%localappdata%\Microsoft\VisualStudio\15.0_xxxxxxxx* 폴더 외부의 위치로 내보냅니다.

1. 업그레이드된 Visual Studio 설치의 **VS 2017용 개발자 명령 프롬프트**를 열고 `devenv /resetuserdata`를 실행합니다.

1. Visual Studio를 시작하고 내보낸 설정 파일에서 저장된 설정을 가져옵니다.

## <a name="see-also"></a>참고 항목

- [IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)
- [환경 설정](../ide/environment-settings.md)
- [환경 > 계정 옵션 대화 상자](reference/accounts-environment-options-dialog-box.md)

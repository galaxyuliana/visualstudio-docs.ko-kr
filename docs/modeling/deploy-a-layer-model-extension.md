---
title: 레이어 모델 확장명 배포
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- dependency diagrams, deploying extensions
- layer models, deploying extensions
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.prod: visual-studio-dev15
ms.openlocfilehash: 1e39463004ddaa30c79cd944710aef56ba1e5498
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55029780"
---
# <a name="deploy-a-layer-model-extension"></a>레이어 모델 확장명 배포

Visual Studio의 다른 사용자는 Visual Studio를 사용하여 만든 레이어 모델링 확장을 설치할 수 있습니다.

## <a name="install-your-extension"></a>확장 설치

확장은 다른 컴퓨터에 설치할 수 있는 VSIX 파일로 컴파일됩니다. 개발 컴퓨터에 설치하여 Visual Studio의 기본 인스턴스에서 확장을 사용할 수 있게 만들 수도 있습니다.

### <a name="to-install-the-extension"></a>확장을 설치하려면

1. 포함 하는 프로젝트에서 **source.vsix.manifest**오픈 합니다 *bin* 파일 탐색기에서 디렉터리입니다.

2. 복사 합니다  **\*.vsix** 확장을 설치 하려는 컴퓨터에는 파일입니다.

3. 대상 컴퓨터에서 Windows 탐색기를 통해 *.vsix 파일을 두 번 클릭합니다.

    VSIX 설치 관리자가 열립니다.

### <a name="to-uninstall-the-extension"></a>확장을 제거하려면

1.  Visual Studio에서에 **도구** 메뉴에서 클릭 **확장 및 업데이트**합니다.

2.  확장의 이름을 클릭 한 다음 클릭 **제거**합니다.

## <a name="install-an-extension-on-team-foundation-server"></a>Team Foundation Server에서 확장을 설치 합니다.

Team Foundation Server 서버 일반적으로 Visual Studio를 설치 하 고, 없고 두 번 클릭 하 여 VSIX를 설치할 수 없습니다 때문입니다. 확장을 수동으로 설치 해야 합니다.

### <a name="to-install-your-layer-extension-on-a-team-foundation-server-server"></a>Team Foundation Server 서버에 레이어 확장을 설치 하려면

1.  복사 합니다. *vsix* 개발 컴퓨터에서 파일을 Team Foundation Server (TFS) 컴퓨터에 있습니다.

     VSIX 파일을 다음 위치 중 하나에 배치합니다.

    -   모든 사용자 및 서비스에 대해 설치하려면

         %ProgramFiles%\Microsoft Visual Studio [version]\Common7\IDE\Extensions\Microsoft

    -   빌드가 실행 되는 네트워크 서비스에 대해서만 설치 하려면:

         %WinDir%\ServiceProfiles\NetworkService\AppData\Local\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

    -   특정 사용자로 대화형 모드에서 실행 되도록 빌드를 구성한 경우 해당 사용자에 대해서만 설치할 수 있습니다.

         %LocalAppData%\Microsoft\VisualStudio\\[version]\Extensions\Microsoft

2.  각 VSIX 파일을 동일한 위치의 폴더로 확장합니다.

    1.  파일 이름 확장명을 변경 **.vsix** 하 **.zip**합니다.

    2.  .zip 파일의 내용을 폴더로 추출합니다.

    3.  .zip 파일을 삭제합니다.

3.  TFS를 다시 시작 합니다.

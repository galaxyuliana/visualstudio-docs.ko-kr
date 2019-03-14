---
title: 원격 디버거 다운로드
description: 원격 디버거에 대 한 다운로드 링크
services: ''
author: mikejo5000
ms.service: ''
ms.topic: include
ms.date: 05/23/2018
ms.author: mikejo
ms.custom: include file
ms.openlocfilehash: 01ec01ad642333d9ee46296cbcb4a02526152e94
ms.sourcegitcommit: 3ca33862c1cfc3ccb83de3e95f1e69e860ab143a
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57526875"
---
원격 장치 또는 서버에 디버그 하려는 하지 않고 Visual Studio 컴퓨터에서 다운로드 한 후 다음 표에 있는 링크에서 올바른 버전의 원격 도구를 설치 합니다.

- Visual Studio의 버전에 대 한 가장 최근의 원격 도구를 다운로드 합니다. 최신 원격 도구 버전은 이전 Visual Studio 버전과 호환 되지만 원격 도구 버전 이후 Visual Studio 버전과 호환 되지 않습니다.
- 설치 하는 컴퓨터와 동일한 아키텍처를 사용 하 여 원격 도구를 다운로드 합니다. 예를 들어, 64 비트 운영 체제를 실행 하는 원격 컴퓨터에서 32 비트 앱을 디버그 하려는 경우 64 비트 원격 도구를 설치 합니다.

::: moniker range=">=vs-2019"

> [!NOTE]
> Visual Studio 2019에 대 한 독립 실행형 원격 도구를 Visual Studio 2019를 사용 하 여 원격 디버거를 사용 해야 하는 경우 사용할 수 있을 때까지 [원격 디버거를 찾을](https://docs.microsoft.com/visualstudio/debugger/remote-debugging?view=vs-2017#fileshare_msvsmon) Visual Studio 2019와의 직접 설치에 복사 하 고 실행 원격 컴퓨터 또는 파일 공유에서 실행 합니다.

::: moniker-end

|버전|링크|참고 사항|
|-|-|-|
|Visual Studio 2017(최신 버전)|[원격 도구](https://visualstudio.microsoft.com/downloads/?q=remote+tools#remote-tools-for-visual-studio-2017)|모든 Visual Studio 2017 버전 호환 됩니다. (X 86, x64 또는 ARM64) 장치 운영 체제와 일치 하는 버전을 다운로드 합니다. Windows Server에서 참조 하세요 [파일 다운로드를 차단 해제](../../debugger/remote-debugging-unblock-file-download.md) 도움말 원격 도구를 다운로드 합니다.|
|Visual Studio 2015|[원격 도구](https://my.visualstudio.com/Downloads?q=remote%20tools%20visual%20studio%202015)|Visual Studio 2015 용 원격 도구 My.VisualStudio.com에서 사용할 수 있습니다. 메시지가 표시 되 면 무료 가입 [Visual Studio Dev Essentials](https://visualstudio.microsoft.com/dev-essentials/) 프로그램 또는 Visual Studio 구독 ID로 로그인 합니다. Windows Server에서 참조 하세요 [파일 다운로드를 차단 해제](../../debugger/remote-debugging-unblock-file-download.md) 도움말 원격 도구를 다운로드 합니다.|
|Visual Studio 2013|[원격 도구](/previous-versions/visualstudio/visual-studio-2013/bt727f1t(v=vs.120)#Installing_the_Remote_Tools)|Visual Studio 2013 설명서에서 페이지를 다운로드 합니다.|
|Visual Studio 2012|[원격 도구](/previous-versions/visualstudio/visual-studio-2012/bt727f1t(v=vs.110)#BKMK_Installing_the_Remote_Tools)|Visual Studio 2012 설명서에서 페이지를 다운로드 합니다.|

복사 하 여 원격 디버거를 실행할 수 있습니다 *msvsmon.exe* 원격 도구를 설치 하는 것이 아니라 원격 컴퓨터에 있습니다. 그러나 원격 디버거 구성 마법사 (*rdbgwiz.exe*)는 원격 도구를 설치할 때에 사용할 수 있습니다. 원격 디버거를 서비스로 실행 하려는 경우 구성 마법사를 사용 해야 합니다. 자세한 내용은 [(선택 사항) 원격 디버거를 서비스로 구성](../../debugger/remote-debugging.md#bkmk_configureService)합니다.

>[!NOTE]
>- ARM 장치에서 Windows 10 앱을 디버깅 하려면 최신 버전의 원격 도구를 사용 하 여 사용할 수 있는, ARM64를 사용 합니다.
>- Windows RT 장치에서 Windows 10 앱을 디버깅 하려면 Visual Studio 2015 원격 도구 다운로드에 사용할 수 있는 ARM을 사용 합니다.

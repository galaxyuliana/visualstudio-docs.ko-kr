---
title: 프로파일링 도구 명령줄 도구의 경로 지정 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 7047bf18-5779-4f6e-872c-66e2fc47c969
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 48ac65ef8fb7a67783a3c9c5a9652accf86821fc
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62979837"
---
# <a name="specify-the-path-to-profiling-tools-command-line-tools"></a>프로파일링 도구 명령줄 도구의 경로 지정

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구 명령줄 도구의 경로가 PATH 환경 변수에 추가되지 않았습니다. 32비트 컴퓨터에는 도구가 단일 디렉터리에 있습니다. 64비트 컴퓨터에는 프로파일링 도구가 32비트 및 64비트 버전으로 있습니다.

## <a name="32-bit-computers"></a>32비트 컴퓨터
::: moniker range=">=vs-2019"
 네이티브 코드의 경우 Visual Studio 프로파일러 API는 *VSPerf.dll*에 있습니다. 헤더 파일, *VSPerf.h* 및 가져오기 라이브러리, *VSPerf.lib*는 *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* 디렉터리에 있습니다.
::: moniker-end
::: moniker range="vs-2017"
 네이티브 코드의 경우 Visual Studio 프로파일러 API는 *VSPerf.dll*에 있습니다. 헤더 파일, *VSPerf.h* 및 가져오기 라이브러리, *VSPerf.lib*는 *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* 디렉터리에 있습니다.
::: moniker-end

 관리되는 코드의 경우 프로파일러 API는 *Microsoft.VisualStudio.Profiler.dll*에 있습니다. 이 DLL은 *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools* 디렉터리에 있습니다.

## <a name="64-bit-computers"></a>64비트 컴퓨터

64비트 컴퓨터에서 프로파일링된 애플리케이션의 대상 플랫폼에 따라 경로를 지정합니다.

::: moniker range=">=vs-2019"
- 32비트 애플리케이션의 경우 기본 프로파일러 도구 디렉터리는 다음과 같습니다.

     (네이티브) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\PerfSDK* (관리) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- 64비트 애플리케이션의 경우 기본 프로파일러 도구가 위치한 디렉터리는 다음과 같습니다.

     (네이티브) *Microsoft Visual Studio\2019\Team Tools\Performance Tools\x64\PerfSDK* (관리) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end

::: moniker range="vs-2017"
- 32비트 애플리케이션의 경우 기본 프로파일러 도구 디렉터리는 다음과 같습니다.

     (네이티브) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\PerfSDK* (관리) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools*

- 64비트 애플리케이션의 경우 기본 프로파일러 도구가 위치한 디렉터리는 다음과 같습니다.

     (네이티브) *Microsoft Visual Studio\2017\Team Tools\Performance Tools\x64\PerfSDK* (관리) *Microsoft Visual Studio\Shared\Common\VSPerfCollectionTools\x64*
::: moniker-end
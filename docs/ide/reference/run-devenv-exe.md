---
title: -Run(devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- /Run Devenv
- Run Devenv switch
- applications [Visual Studio], running
- /R Devenv switch
- Devenv, /Run switch
- R Devenv switch (/R)
ms.assetid: b1f22f9d-39a5-4918-8a2a-4b5c1e872665
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 0d8e89a223ef43d7d2235772940a05b7fb42c0f8
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54996339"
---
# <a name="run-devenvexe"></a>/Run (devenv.exe)

지정한 프로젝트 또는 솔루션을 컴파일하고 실행합니다.

## <a name="syntax"></a>구문

```shell
devenv {/Run|/R} {SolutionName|ProjectName} [/Out OutputFilename]
```

## <a name="arguments"></a>인수

- *SolutionName*

  솔루션 파일의 전체 경로 및 이름입니다.

- *ProjectName*

  프로젝트 파일의 전체 경로 및 이름입니다.

- `/Out` *OutputFilename*

  선택 사항입니다. 도구의 출력을 보낼 파일의 이름입니다. 파일이 이미 있는 경우 출력은 파일의 끝에 추가됩니다.

## <a name="remarks"></a>주의

활성 솔루션 구성에 대해 지정된 설정에 따라 지정된 프로젝트 또는 솔루션을 컴파일하고 실행합니다. 이 스위치는 IDE를 시작하고 프로젝트 또는 솔루션 실행이 완료된 후 활성 상태로 둡니다.

- 공백을 포함하는 문자열은 큰따옴표로 묶습니다.

- 오류를 포함한 요약 정보는 **명령** 창 또는 `/Out` 스위치로 지정된 로그 파일에 표시할 수 있습니다.

## <a name="example"></a>예제

이 예제에서는 활성 배포 구성을 사용하여 `MySolution` 솔루션을 실행합니다.

```shell
devenv /run "%USERPROFILE%\source\repos\MySolution\MySolution.sln"
```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)
- [/Runexit (devenv.exe)](../../ide/reference/runexit-devenv-exe.md)
- [/Build (devenv.exe)](../../ide/reference/build-devenv-exe.md)
- [/Rebuild (devenv.exe)](../../ide/reference/rebuild-devenv-exe.md)
- [/Out (devenv.exe)](../../ide/reference/out-devenv-exe.md)
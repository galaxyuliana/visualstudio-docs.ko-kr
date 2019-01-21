---
title: -SafeMode(devenv.exe)
ms.date: 12/10/2018
ms.prod: visual-studio-dev15
ms.topic: reference
helpviewer_keywords:
- /SafeMode Devenv switch
- Devenv, /SafeMode switch
- SafeMode switch
ms.assetid: b191f6a5-8f12-47ec-bcc7-b68149a22aa8
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 092cc1fc3267113e862646b7572e9091b8f6ddef
ms.sourcegitcommit: 01185dadd2fa1f9a040d2a366869f1a5e1d18e0f
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/11/2019
ms.locfileid: "54227202"
---
# <a name="safemode-devenvexe"></a>/SafeMode(devenv.exe)

안전 모드에서 Visual Studio를 시작하고 기본 환경 및 서비스만 로드합니다.

## <a name="syntax"></a>구문

```shell
devenv /SafeMode
```

## <a name="remarks"></a>주의

이 스위치는 Visual Studio가 시작될 때 모든 타사 VSPackages의 로드를 차단하여 안정적으로 실행될 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 안전 모드에서 Visual Studio를 시작합니다.

```shell
devenv /safemode
```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)
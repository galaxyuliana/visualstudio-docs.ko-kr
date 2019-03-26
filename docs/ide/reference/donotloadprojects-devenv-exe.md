---
title: -DoNotLoadProjects(devenv.exe)
ms.date: 03/11/2019
ms.topic: reference
helpviewer_keywords:
- Devenv, /DoNotLoadProjects switch
- /DoNotLoadProjects Devenv switch
- DoNotLoadProjects Devenv switch
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 91c4da26d202e1a23ff70a7c655f64fd6c05a340
ms.sourcegitcommit: f7c401a376ce410336846835332a693e6159c551
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2019
ms.locfileid: "57875400"
---
# <a name="donotloadprojects-devenvexe"></a>/DoNotLoadProjects(devenv.exe)

프로젝트를 로드하지 않고 지정된 솔루션을 엽니다.

## <a name="syntax"></a>구문

```shell
devenv /DoNotLoadProjects SolutionName
```

## <a name="arguments"></a>인수

- *SolutionName*

  필수 요소. 열려는 솔루션의 전체 경로 및 이름입니다.

## <a name="example"></a>예제

예제에서는 프로젝트를 로드하지 않고 MySln.sln 솔루션을 엽니다.

```shell
devenv /donotloadprojects MySln.sln

```

## <a name="see-also"></a>참고 항목

- [Devenv 명령줄 스위치](../../ide/reference/devenv-command-line-switches.md)

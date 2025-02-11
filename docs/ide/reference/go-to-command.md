---
title: 이동 명령
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- edit.goto
helpviewer_keywords:
- Debug.Goto command
- Go To command
ms.assetid: 201e1dd2-6701-467d-8cc1-faec2ef20511
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9bdc1c97d35b79fec40bbaf8994176cfbb27b8e8
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68919227"
---
# <a name="go-to-command"></a>이동 명령
지정된 줄로 커서를 이동합니다.

## <a name="syntax"></a>구문

```cmd
Edit.GoTo [linenumber]
```

## <a name="arguments"></a>인수
`linenumber`\
선택 사항입니다. 이동할 줄 번호를 나타내는 정수입니다.

## <a name="remarks"></a>설명
줄 번호는 1부터 시작합니다. `linenumber` 값이 1보다 작은 경우 첫 번째 줄이 표시됩니다. `linenumber` 값이 마지막 줄 번호보다 큰 경우 마지막 줄이 표시됩니다.

`linenumber` 값이 지정되지 않으면 **줄 이동** 대화 상자가 표시됩니다.

이 명령에 대한 별칭은 GoToLn입니다.

## <a name="example"></a>예

```cmd
>Edit.GoTo 125
```

## <a name="see-also"></a>참고 항목

- [Visual Studio 명령](../../ide/reference/visual-studio-commands.md)
- [명령 창](../../ide/reference/command-window.md)
- [찾기/명령 상자](../../ide/find-command-box.md)
- [Visual Studio Command Aliases](../../ide/reference/visual-studio-command-aliases.md)
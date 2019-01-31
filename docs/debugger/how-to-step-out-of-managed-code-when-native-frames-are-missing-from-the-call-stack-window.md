---
title: 프로시저 나가기 C# 호출 스택에서 네이티브 프레임이 없을 때 코드 | Microsoft Docs
ms.custom: seodec18
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
- JScript
- SQL
helpviewer_keywords:
- Call Stack window, missing native frames
- code, managed code
- native frames
- stepping, out of managed code
- managed code, stepping out of
ms.assetid: 97cdd2a8-02a9-4a06-a5b1-c92b1e431979
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 25021f0c3daffdaf59633fdb9bff0e2659f43d2e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55043027"
---
# <a name="how-to-step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-window"></a>방법: 호출 스택 창에 네이티브 프레임이 없을 때 관리 코드에서 나가기

**호출 스택** 창에 표시되지 않는 네이티브 프레임이 코드에 있는 경우 관리 코드에서 나가면 예기치 않은 결과가 발생할 수 있습니다. **프로시저 나가기** 대신 중단점을 사용하면 이 문제를 해결할 수 있습니다.

> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [재설정 설정](../ide/environment-settings.md#reset-settings)을 참조하세요.

## <a name="step-out-of-managed-code-when-native-frames-are-missing-from-the-call-stack-display"></a>네이티브 프레임이 호출 스택 화면에서 없어질 경우 관리 코드의 프로시저 나가기

1.  네이티브 코드에서 호출 후의 위치 중단점을 관리 코드로 설정합니다.

2.  **디버그** 메뉴에서 **계속**을 선택합니다.

     관리되는 호출이 완료되면 네이티브 코드의 중단점에서 실행이 중지됩니다.

## <a name="see-also"></a>참고 항목

- [방법: 호출 스택 창 사용](../debugger/how-to-use-the-call-stack-window.md)
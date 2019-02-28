---
title: '오류: 원격 컴퓨터 DCOM 통신을 시작 하지 못했습니다. | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.unmarshal_callback_failed
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9e936292010c73decffadc5b215156f2200ed8b3
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56683076"
---
# <a name="error-remote-computer-could-not-initiate-dcom-communications"></a>오류: 원격 컴퓨터에서 DCOM 통신을 시작하지 못했습니다.
원격 컴퓨터에서 로컬 컴퓨터와 통신을 시도하는 동안 DCOM 오류가 발생했습니다. Visual Studio에서 실행되는 컴퓨터는

 로컬 컴퓨터입니다. 여러 가지 원인에 의해 이런 오류가 발생할 수 있습니다.

-   로컬 컴퓨터에서 방화벽을 사용하고 있습니다.

-   원격 컴퓨터에서 로컬 컴퓨터에 대한 Windows 인증이 작동하지 않습니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

1.  로컬 컴퓨터에서 Windows 방화벽을 사용 하는 경우 참조 [원격 디버깅](../debugger/remote-debugging.md) 로컬 디버깅을 위해 방화벽을 구성 하는 방법에 대 한 지침에 대 한 합니다.

2.  원격 서버에서 로컬 컴퓨터의 파일 공유 위치를 열어 Windows 인증을 테스트합니다.

3.  Windows 인증을 복원하려면 두 컴퓨터를 모두 다시 부팅합니다. 로컬 컴퓨터와 원격 컴퓨터에서 이벤트 로그를 검사하여 Kerberos 오류가 있는지 확인하고 알려진 문제가 있는지 도메인 관리자에게 문의합니다.

## <a name="see-also"></a>참고 항목
 [Remote Debugging](../debugger/remote-debugging.md)
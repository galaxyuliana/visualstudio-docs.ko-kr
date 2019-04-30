---
title: 보안 문제 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- security [Debugging SDK]
- debugging [Debugging SDK], security
ms.assetid: d6ffff0a-afb4-4f38-86d8-476c881c4e4b
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5f68db1a4c6fb3ea2a7f9542c1a9d2d313359554
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62913110"
---
# <a name="security-issues"></a>보안 문제
Visual Studio를 사용 하 여 프로그램을 디버깅 하려면 필요한 권한만 개발자 프로그램을 실행 해야 하는 것과 같은 됩니다. 대부분의 상황에 대 한 원격 디버깅 포함 됩니다. 인터넷 정보 서비스와 같은 다른 서비스와 관련 된 몇 가지 상황에는 높은 수준의 사용 권한이 필요할 수 있습니다.

 Visual Studio를 실행 하는 동안 프로세스 디버그 관리자 (PDM) 로컬 컴퓨터에서 디버그 프로세스를 추적 합니다. 호출 프로그램을 원격으로 *msvsmon.exe* 원격 디버깅을 처리 하 여 PDM를 사용할 수 있도록 하는 개발자에 의해 시작 됩니다. (*msvsmon.exe* 서비스와 해당 컴퓨터에서 원격 디버깅을 사용 하려면 수동으로 시작 해야 합니다.) 때 Visual Studio (또는 *msvsmon.exe*)가 실행 되지 않는 프로세스 없음 디버깅에 대 한 추적 됩니다.

 개발자는 특별 한 권한 없이 시작 하는 프로그램을 디버깅할 수 있습니다. 개발자는 다른 사용자는 동일한 보안 그룹의 멤버인 경우 다른 사용자가 시작한 프로세스를 디버깅할 수도 수 있습니다. 이며, 원격 디버깅을 사용 하려면 원격 컴퓨터에 필요한 파일을 복사 하 고 시작에 필요한 *msvsmon.exe*합니다. 자세한 내용은 [원격 디버깅](../../debugger/remote-debugging.md)합니다.

## <a name="see-also"></a>참고자료
- [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)
- [프로세스 디버그 관리자](../../extensibility/debugger/process-debug-manager.md)
- [원격 디버깅](../../debugger/remote-debugging.md)

---
title: Microsoft Visual Studio 원격 디버깅 모니터에 연결할 수 없습니다. Microsoft Docs
ms.date: 08/24/2017
ms.topic: reference
f1_keywords:
- vs.debug.error.remote_debug
- vs.debug.error.firewall.remotemachine
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
ms.openlocfilehash: c42cdfc5c3f3c0267fdcbdfca8ddc4bb30663384
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924534"
---
# <a name="unable-to-connect-to-the-microsoft-visual-studio-remote-debugging-monitor"></a>Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor
이 메시지는 원격 컴퓨터에 원격 디버깅 모니터가 올바르게 설치 되지 않았거나 네트워크 문제나 방화벽으로 인해 원격 컴퓨터에 액세스할 수 없는 경우에 발생할 수 있습니다.

> [!IMPORTANT]
> 제품 버그로 인해이 메시지가 수신 되었다고 생각 되는 경우 [이 문제](../ide/how-to-report-a-problem-with-visual-studio.md) 를 Visual Studio에 보고 하세요. 자세한 도움말이 필요한 경우 [Talk to Us](../ide/talk-to-us.md) 에서 Microsoft에 문의하는 방법을 참조하세요.

## <a name="specificerrors"></a>자세한 오류 메시지는 무엇입니까?

일반 `Unable to Connect to the Microsoft Visual Studio Remote Debugging Monitor` 메시지입니다. 일반적으로 보다 구체적인 메시지는 오류 문자열에 포함 되며 문제의 원인을 파악 하는 데 도움이 될 수 있으며 보다 정확한 수정 사항을 검색 하는 데 도움이 될 수 있습니다. 다음은 기본 오류 메시지에 추가 되는 몇 가지 일반적인 오류 메시지입니다.

- [디버거가 원격 컴퓨터에 연결할 수 없습니다. 디버거가 지정 된 컴퓨터 이름을 확인할 수 없습니다.](#cannot_connect)
- [원격 디버거가 연결 요청을 거부 했습니다.](#rejected)
- [메모리 위치에 대 한 잘못 된 액세스](#invalid_access)
- [지정 된 이름의 서버가 원격 컴퓨터에서 실행 되 고 있지 않습니다.](#no_server)
- [요청 된 이름이 올바르지만 요청 된 형식의 데이터를 찾을 수 없습니다.](#valid_name)
- [대상 컴퓨터의 Visual Studio 원격 디버거이 컴퓨터에 다시 연결할 수 없습니다.](#cant_connect_back)
- [액세스 거부됨](#access_denied)
- [보안 패키지 특정 오류가 발생 했습니다.](#security_package)

## <a name="cannot_connect"></a>디버거가 원격 컴퓨터에 연결할 수 없습니다. 디버거가 지정 된 컴퓨터 이름을 확인할 수 없습니다.

다음 단계를 수행 합니다.

1. **프로세스에 연결** 대화 상자 또는 프로젝트 속성 (속성을 설정 하려면 [다음 단계](#server_incorrect)참조)에 올바른 컴퓨터 이름 및 포트 번호를 입력 해야 합니다. 컴퓨터 이름은 다음과 같은 형식 이어야 합니다.

    `computername:port`

    > [!NOTE]
    > 포트 번호는 대상 컴퓨터에서 실행 되 고 *있어야* 하는 [원격 디버거의 포트 번호](../debugger/remote-debugger-port-assignments.md)와 일치 해야 합니다.

2. 컴퓨터 이름이 작동 하지 않는 경우 IP 주소와 포트 번호를 대신 사용해 보세요.

3. 대상 컴퓨터에서 실행 되는 원격 디버거 버전이 Visual Studio 버전과 일치 하는지 확인 합니다. 올바른 버전의 원격 디버거를 가져오려면 [원격 디버깅](../debugger/remote-debugging.md)을 참조 하세요.

    > [!TIP]
    > 프로세스에 연결 하 고 성공적으로 연결 했지만 원하는 프로세스가 표시 되지 않는 경우 **모든 사용자의 프로세스 표시 확인란**을 선택 합니다. 이렇게 하면 다른 사용자 계정으로 연결 되어 있는 경우 프로세스가 표시 됩니다.

4. 이러한 단계를 수행 해도이 오류가 해결 되지 않으면 [원격 컴퓨터에 연결할 수 없습니다](#dns).를 참조 하세요.

## <a name="rejected"></a>원격 디버거가 연결 요청을 거부 했습니다.

**프로세스에 연결** 대화 상자 또는 프로젝트 속성에서 원격 컴퓨터 이름과 포트 번호가 원격 디버거 창에 표시 된 이름 및 포트 번호와 일치 하는지 확인 합니다. 잘못 된 경우 문제를 해결 하 고 다시 시도 하세요.

이러한 값이 올바르고 메시지가 **Windows 인증** 모드를 언급 하는 경우 원격 디버거가 올바른 인증 모드 (**도구 > 옵션**)에 있는지 확인 합니다.

## <a name="invalid_access"></a>메모리 위치에 대 한 잘못 된 액세스

내부 오류가 발생했습니다. Visual Studio를 다시 시작 하 고 다시 시도 하세요.

## <a name="no_server"></a>지정 된 이름의 서버가 원격 컴퓨터에서 실행 되 고 있지 않습니다.

Visual Studio에서 원격 디버거에 연결할 수 없습니다. 이 메시지는 다음과 같은 여러 가지 이유로 발생할 수 있습니다.

- 원격 디버거가 다른 사용자 계정으로 실행 되 고 있을 수 있습니다. [다음 단계](#user_accounts) 를 참조 하세요.

- 포트가 방화벽에서 차단 됩니다. 특히 타사 방화벽을 사용 하는 경우 방화벽에서 [요청을 차단 하지](#firewall)않는지 확인 합니다.

- 원격 디버거 버전이 Visual Studio와 일치 하지 않습니다. 올바른 버전의 원격 디버거를 가져오려면 [원격 디버깅](../debugger/remote-debugging.md)을 참조 하세요.

## <a name="valid_name"></a>요청 된 이름이 올바르지만 요청 된 형식의 데이터를 찾을 수 없습니다.

원격 컴퓨터가 있지만 Visual Studio가 원격 디버거에 연결할 수 없습니다. 이 메시지는 다음과 같은 여러 가지 이유로 발생할 수 있습니다.

- DNS 문제로 인해 연결할 수 없습니다. [이러한 단계](#dns)를 참조 하세요.

- 원격 디버거가 다른 사용자 계정으로 실행 되 고 있을 수 있습니다. [이러한 단계](#user_accounts)를 수행합니다.

- 포트가 방화벽에서 차단 됩니다. 특히 타사 방화벽을 사용 하는 경우 방화벽에서 [요청을 차단 하지](#firewall)않는지 확인 합니다.

- 원격 디버거 버전이 Visual Studio와 일치 하지 않습니다. 올바른 버전의 원격 디버거를 가져오려면 [원격 디버깅](../debugger/remote-debugging.md)을 참조 하세요.

## <a name="cant_connect_back"></a>대상 컴퓨터의 Visual Studio 원격 디버거이 컴퓨터에 다시 연결할 수 없습니다.

원격 디버거가 다른 사용자 계정으로 실행 되 고 있을 수 있습니다. 원격 디버거에서 **도구 > 사용 권한을** 열어 원격 디버거의 사용 권한에 사용자를 추가 합니다. 자세한 내용은 [원격 디버거가 다른 사용자 계정으로 실행 되](#user_accounts)고 있는지 확인 하세요.

오류 메시지가 방화벽을 언급 하는 경우 로컬 컴퓨터의 방화벽이 원격 컴퓨터에서 다시 Visual Studio로의 통신을 차단 하는 것일 수 있습니다. [이러한 단계](#firewall)를 참조 하세요.

## <a name="access_denied"></a> 액세스 거부됨

32 비트 컴퓨터 (지원 되지 않음)에서 64 비트 원격 컴퓨터에 대 한 디버깅을 시도 하는 경우이 오류가 표시 될 수 있습니다.

## <a name="security_package"></a>보안 패키지 특정 오류가 발생 했습니다.

이는 Windows XP 및 Windows 7과 관련 된 레거시 문제일 수 있습니다. 이 [정보](https://stackoverflow.com/questions/4786016/unable-to-connect-to-the-microsoft-remote-debugging-monitor-a-security-package)를 참조 하세요.

## <a name="causes-and-recommendations"></a>원인 및 권장 사항

### <a name="dns"></a> 원격 머신에 연결할 수 없음

원격 컴퓨터 이름을 사용 하 여 연결할 수 없는 경우 IP 주소를 대신 사용해 보세요. 원격 컴퓨터의 `ipconfig` 명령줄에서를 사용 하 여 IPv4 주소를 가져올 수 있습니다. HOSTS 파일을 사용 하는 경우 올바르게 구성 되어 있는지 확인 합니다.

이 작업이 실패 하면 네트워크에서 원격 컴퓨터에 액세스할 수 있는지 확인 합니다 (원격 컴퓨터[ping](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee624059(v=ws.10)) ). 일부 Microsoft Azure 시나리오의 경우를 제외 하 고는 인터넷을 통한 원격 디버깅이 지원 되지 않습니다.

### <a name="server_incorrect"></a>서버 이름이 잘못 되었거나 타사 소프트웨어가 원격 디버거를 방해 합니다.

Visual Studio에서 프로젝트 속성을 확인 하 고 서버 이름이 올바른지 확인 합니다. [ C# 및 Visual Basic](../debugger/remote-debugging-csharp.md#remote_csharp) 에 대 한 항목 [C++](../debugger/remote-debugging-cpp.md#remote_cplusplus)을 참조 하세요. ASP.NET의 경우 프로젝트 형식에 따라 **속성/웹/서버** 또는 **속성/디버그** 를 엽니다.

> [!NOTE]
> 프로세스에 연결 하는 경우 프로젝트 속성의 원격 설정이 사용 되지 않습니다.

서버 이름이 올바르면 바이러스 백신 소프트웨어나 타사 방화벽이 원격 디버거를 차단할 수 있습니다. 로컬로 디버그할 때 이러한 현상이 발생할 수 있습니다. Visual Studio가 32 비트 응용 프로그램이 기 때문에 64 비트 버전의 원격 디버거를 사용 하 여 64 비트 응용 프로그램을 디버그 하는 경우에 발생할 수 있습니다. 32 비트 및 64 비트 프로세스는 로컬 컴퓨터 내의 로컬 네트워크를 사용 하 여 통신 합니다. 컴퓨터에서 나가는 네트워크 트래픽이 없지만 타사 보안 소프트웨어가 통신을 차단할 수 있습니다.

### <a name="user_accounts"></a> 원격 디버거가 다른 사용자 계정으로 실행되고 있음

원격 디버거는 기본적으로 원격 디버거를 시작한 사용자와 Administrators 그룹의 멤버 에서만 연결을 허용 합니다. 추가 사용자에 게 사용 권한을 명시적으로 부여 해야 합니다.

다음 방법 중 하나를 사용하여 이 문제를 해결할 수 있습니다.

- 원격 디버거의 사용 권한에 Visual Studio 사용자를 추가 합니다 (원격 디버거 창에서 **도구 > 권한**선택).

- 원격 컴퓨터에서 Visual Studio 컴퓨터에서 사용 하는 것과 동일한 사용자 계정 및 암호를 사용 하 여 원격 디버거를 다시 시작 합니다.

    > [!NOTE]
    > 원격 서버에서 원격 디버거를 실행 하는 경우 원격 디버거 앱을 마우스 오른쪽 단추로 클릭 하 고 **관리자 권한으로 실행** 을 선택 합니다. 또는 원격 디버거를 서비스로 실행할 수 있습니다. 원격 서버에서 실행 하지 않는 경우에는 정상적으로 시작 하면 됩니다.

- **/allow \<사용자 이름>** 매개 변수를 사용하여 명령줄에서 원격 디버거를 시작할 수 있습니다`msvsmon /allow <username@computer>`.

- 또는 모든 사용자가 원격 디버깅을 수행 하도록 허용할 수 있습니다. 원격 디버거 창에서 **도구 > 옵션** 대화 상자로 이동합니다. **인증 안 함**을 선택하는 경우 **모든 사용자가 디버깅할 수 있도록 허용**을 선택할 수 있습니다. 그러나 다른 옵션이 실패 하거나 개인 네트워크에 있는 경우에만이 옵션을 시도해 야 합니다.

### <a name="firewall"></a> 원격 머신의 방화벽이 원격 디버거로 들어오는 연결을 허용하지 않음
 Visual Studio와 원격 디버거 간의 통신을 허용하도록 Visual Studio 컴퓨터의 방화벽 및 원격 컴퓨터의 방화벽을 구성해야 합니다. 원격 디버거에서 사용 중인 포트에 대한 자세한 내용은 [Remote Debugger Port Assignments](../debugger/remote-debugger-port-assignments.md)을 참조하세요. Windows 방화벽을 구성하는 방법에 대한 자세한 내용은 [Configure the Windows Firewall for Remote Debugging](../debugger/configure-the-windows-firewall-for-remote-debugging.md)을 참조하세요.

### <a name="the-version-of-the-remote-debugger-doesnt-match-the-version-of-visual-studio"></a>원격 디버거 버전이 Visual Studio 버전과 일치하지 않음
 로컬로 실행하는 Visual Studio 버전이 원격 컴퓨터에서 실행되는 원격 디버깅 모니터 버전과 일치해야 합니다. 이 문제를 해결하려면 일치하는 버전의 원격 디버깅 모니터를 다운로드하여 설치합니다. 올바른 버전의 원격 디버거를 가져오려면 [원격 디버깅](../debugger/remote-debugging.md)을 참조 하세요.

### <a name="the-local-and-remote-machines-have-different-authentication-modes"></a>로컬 및 원격 컴퓨터의 인증 모드가 서로 다름
 로컬 및 원격 컴퓨터에서 동일한 인증 모드를 사용해야 합니다. 이 문제를 해결하려면 두 컴퓨터에서 모두 동일한 인증 모드를 사용 중인지 확인합니다. 인증 모드를 변경할 수 있습니다. 원격 디버거 창에서 **도구 > 옵션** 대화 상자로 이동 합니다.

 인증 모드에 대한 자세한 내용은 [Windows 인증 개요](/previous-versions/windows/it-pro/windows-server-2012-R2-and-2012/hh831472(v=ws.11))를 참조하세요.

### <a name="anti-virus-software-is-blocking-the-connections"></a>바이러스 백신 소프트웨어가 연결을 차단함
 Windows 바이러스 백신 소프트웨어는 원격 디버거 연결을 허용하지만 일부 타사 바이러스 백신 소프트웨어가 차단할 수도 있습니다. 이러한 연결을 허용하는 방법을 알아보려면 해당 바이러스 백신 소프트웨어에 대한 설명서를 확인합니다.

### <a name="network-security-policy-is-blocking-communication-between-the-remote-machine-and-visual-studio"></a>네트워크 보안 정책에서 원격 컴퓨터와 Visual Studio 간의 통신을 차단함
 네트워크 보안을 검토하여 통신을 차단하지 않는지 확인합니다. Windows 네트워크 보안 정책에 대 한 자세한 내용은 [보안 정책 설정](/windows/device-security/security-policy-settings/security-policy-settings)을 참조 하세요.

### <a name="the-network-is-too-busy-to-support-remote-debugging"></a>네트워크 사용량이 너무 많아 원격 디버깅을 지원할 수 없음
 다른 시간에 원격 디버깅을 수행하거나 다른 시간에 네트워크 작업을 다시 예약해야 할 수도 있습니다.

## <a name="more-help"></a>자세한 도움말
 원격 디버거 도움말을 더 얻으려면 원격 디버거의 도움말 페이지를 엽니다 (원격 디버거의**도움말 > 사용** ).

## <a name="see-also"></a>참고 항목
- [Remote Debugging](../debugger/remote-debugging.md)

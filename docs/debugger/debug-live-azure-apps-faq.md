---
title: 스냅숏 디버깅 FAQ | Microsoft Docs
ms.date: 11/07/2017
ms.topic: reference
helpviewer_keywords:
- debugger
ms.assetid: 944f1eb0-a74b-4d28-ae2b-a370cd869add
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 7ea593ad5f88ba29f6b1c0d7c64a129b8f71c7f5
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58857076"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Visual Studio의 스냅숏 디버깅에 대해 자주 묻는 질문

다음은 스냅숏 디버거를 사용하여 라이브 Azure 애플리케이션을 디버그할 때 나올 수 있는 질문 목록입니다.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>스냅숏 생성 시 어떤 성능 저하가 발생하나요?

스냅숏 디버거는 앱의 스냅숏을 캡처할 때 앱 프로세스를 포크하고 포크된 복사본을 일시중단합니다. 스냅숏을 디버그하는 경우 포크된 프로세스 복사본에 대해 디버그합니다. 이 프로세스는 10~20밀리초밖에 안 걸리지만 앱의 전체 힙을 복사하지는 않습니다. 페이지 테이블만 복사하고 페이지를 쓰기 작업 중 복사하도록 설정합니다. 힙의 앱 개체 중 일부가 변경되면 해당 페이지가 복사됩니다. 따라서 각 스냅숏은 메모리 내 비용을 적은 양만 차지합니다(대부분 앱의 경우 대략 수백 킬로바이트).

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>확장형 Azure App Service(내 앱의 인스턴스가 여러 개)가 있는 경우는 어떻게 되나요?

앱 인스턴스가 여러 개인 경우 모든 단일 인스턴스에 snappoint가 적용됩니다. 지정된 조건으로 적중된 첫 번째 snappoint만 스냅숏을 만듭니다. snappoint가 여러 개인 경우 이후의 스냅숏은 첫 번째 스냅숏을 만든 인스턴스와 동일한 인스턴스에서 가져옵니다. 출력 창으로 보낸 logpoint는 한 인스턴스의 메시지만 보여 주는 반면, 애플리케이션 로그로 보낸 logpoint는 모든 인스턴스의 메시지를 보냅니다.

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>스냅숏 디버거가 기호를 로드하는 방법은 무엇인가요?

스냅숏 디버거를 사용하려면 로컬 또는 Azure App Service에 배포된 애플리케이션에 대해 일치하는 기호가 있어야 합니다. (포함 PDB는 현재 지원되지 않습니다.) 스냅숏 디버거는 자동으로 Azure App Service에서 기호를 다운로드합니다. Visual Studio 2017 버전 15.2부터 Azure App Service에 배포하는 경우 앱의 기호도 배포합니다.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>스냅숏 디버거가 내 애플리케이션의 릴리스 빌드에 대해 작동하나요?

예, 스냅숏 디버거는 릴리스 빌드에 대해 작동하도록 설계되었습니다. snappoint가 함수에 배치되면 해당 함수가 디버그 버전으로 다시 컴파일되어 디버그할 수 있게 됩니다. 스냅숏 디버거를 중지하면 해당 릴리스 빌드 버전에 대해 함수를 반환합니다.

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>logpoint가 내 프로덕션 애플리케이션에서 부작용을 일으킬 수 있나요?

아니요, 앱에 추가하는 모든 로그 메시지는 가상으로 평가됩니다. 애플리케이션에서 어떠한 부작용도 일으킬 수 없습니다. 하지만 일부 네이티브 속성은 logpoint로 액세스할 수 없습니다.

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>내 서버가 로드 중인 경우 스냅숏 디버거가 작동하나요?

예, 로드 중인 서버에 대해 스냅숏 디버깅이 작동할 수 있습니다. 스냅숏 디버거는 서버에 사용 가능한 메모리가 적은 상황에서는 스냅숏을 제한하고 캡처하지 않습니다.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>스냅숏 디버거를 제거하는 방법은 무엇인가요?

다음 단계를 사용하여 App Service에서 스냅숏 디버거 사이트 확장을 제거할 수 있습니다.

1. Visual Studio 또는 Azure Portal에서 클라우드 탐색기를 통해 App Service를 끕니다.
1. App Service의 Kudu 사이트(즉, yourappservice.**scm**.azurewebsites.net)로 이동한 후 **사이트 확장**으로 이동합니다.
1. 스냅숏 디버거 사이트 확장에서 X를 클릭하여 제거합니다.

#### <a name="why-are-ports-opened-during-a-snapshot-debugger-session"></a>스냅숏 디버거 세션 중에 포트가 열려 있는 이유는 무엇인가요?

Azure에서 생성된 스냅숏을 디버그하려면 스냅숏 디버거에서 일련의 포트를 열어야 하며 이러한 포트는 원격 디버깅에 필요한 포트와 동일합니다. [여기에서 포트 목록을 찾을 수 있습니다](../debugger/remote-debugger-port-assignments.md).

## <a name="see-also"></a>참고 항목

- [Visual Studio의 디버깅](../debugger/index.md)
- [스냅숏 디버거를 사용하여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)
- [스냅숏 디버거를 사용하여 라이브 ASP.NET Azure Virtual Machines\Virtual Machines Scale Sets 디버그](../debugger/debug-live-azure-virtual-machines.md)
- [스냅숏 디버거를 사용하여 라이브 ASP.NET Azure Kubernetes 디버그](../debugger/debug-live-azure-kubernetes.md)
- [스냅숏 디버깅에 대한 문제 해결 및 알려진 문제](../debugger/debug-live-azure-apps-troubleshooting.md)
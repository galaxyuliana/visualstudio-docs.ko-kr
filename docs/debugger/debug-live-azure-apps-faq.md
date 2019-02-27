---
title: 스냅숏 디버깅에 대 한 FAQ | Microsoft Docs
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
ms.openlocfilehash: f5b6315ba3cc99b60c97e70621f42cf13f6397c9
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56630719"
---
# <a name="frequently-asked-questions-for-snapshot-debugging-in-visual-studio"></a>Visual Studio에서 스냅숏 디버깅에 대 한 자주 묻는 질문

스냅숏 디버거를 사용 하 여 라이브 Azure 응용 프로그램을 디버깅할 때 제기 될 수 있습니다 하는 질문 목록은 다음과 같습니다.

#### <a name="what-is-the-performance-cost-of-taking-a-snapshot"></a>스냅숏을 만드는 성능 비용은 얼마 인가요?

스냅숏 디버거는 앱의 스냅숏을 캡처한 응용 프로그램의 프로세스를 분기과 분기 된 복사본을 일시 중단 됩니다. 스냅숏을 디버깅 하는 경우 프로세스의 포크 된 복사본에 대해 디버깅 하는 합니다. 이 프로세스만 10 ~ 20 밀리초가 걸리지만 앱의 전체 힙 복사 하지 않습니다. 대신 페이지 테이블만 복사 하 고 쓰기 시 복사 페이지를 설정 합니다. 힙 변경 시 앱의 개체의 일부를 각 페이지는 복사 됩니다. 따라서 각 스냅숏은 작은 메모리 비용 (대부분의 응용 프로그램 (킬로바이트) 수백) 순서를 포함 됩니다.

#### <a name="what-happens-if-i-have-a-scaled-out-azure-app-service-multiple-instances-of-my-app"></a>규모가 확장 된 Azure App Service (내 앱의 여러 인스턴스)이 있으면 어떻게 되나요?

앱의 여러 인스턴스가 있는 경우 snappoint 모든 단일 인스턴스에 적용 합니다. 지정 된 조건을 적중를 첫 번째 snappoint에만 스냅숏을 만듭니다. 여러 snappoint를 설정한 경우 후속 스냅숏은 첫 번째 스냅숏을 생성 하는 동일한 인스턴스에서 제공 됩니다. Logpoint 출력 창에 전송 되지만 logpoint 응용 프로그램 로그를 보낼 모든 인스턴스에서 메시지를 보내는 인스턴스로, 메시지를에서 표시 됩니다.

#### <a name="how-does-the-snapshot-debugger-load-symbols"></a>스냅숏 디버거 기호를 로드 하는 방법

스냅숏 디버거는 Azure App Service에 로컬 컴퓨터 또는 배포 된 응용 프로그램에 대 한 일치 하는 기호를가 필요 합니다. (Embedded Pdb 현재 지원 되지 않습니다.) 스냅숏 디버거는 자동으로 Azure App Service에서 기호를 다운로드합니다. Visual Studio 2017 버전 15.2, 또한 Azure App Service에 배포할 앱의 기호를 배포 합니다.

#### <a name="does-the-snapshot-debugger-work-against-release-builds-of-my-application"></a>스냅숏 디버거 내 응용 프로그램의 릴리스 빌드에 대해 작동 합니까?

예-스냅숏 디버거는 릴리스 빌드에 대해 작동 하도록 것입니다. 함수에서 snappoint 넣으면 함수를 쉽게 디버깅할 수 있는 디버그 버전으로 다시 컴파일됩니다. 스냅숏 디버거를 중지 하면 함수는 해당 릴리스 빌드에 반환 됩니다.

#### <a name="can-logpoints-cause-side-effects-in-my-production-application"></a>Logpoint은 프로덕션 응용 프로그램에서 부작용을 일으킬 수 있습니까?

아니요-앱에 추가 된 로그 메시지는 사실상 평가 됩니다. 응용 프로그램에서 부작용 문제를 일으킬 수 없습니다. 있습니다. 그러나 일부 네이티브 속성 logpoint를 사용 하 여 액세스할 수 있습니다.

#### <a name="does-the-snapshot-debugger-work-if-my-server-is-under-load"></a>My server는 부하가 있는 경우 스냅숏 디버거 작동 하나요?

예, 부하 상태에서 서버에 대 한 스냅숏 디버깅 작업할 수 있습니다. 스냅숏 디버거 제한 및 경우에는 스냅숏을 캡처하지 않습니다 서버에서 낮은 크기의 사용 가능한 메모리를 부족 합니다.

#### <a name="how-do-i-uninstall-the-snapshot-debugger"></a>스냅숏 디버거를 제거 하려면 어떻게 해야 합니까?

다음 단계를 사용 하 여 App Service에서 스냅숏 디버거 사이트 확장을 제거할 수 있습니다.

1. Visual Studio 또는 Azure portal에서 클라우드 탐색기를 통해 서비스 앱을 해제 합니다.
1. App Service의 Kudu 사이트로 이동 (즉, yourappservice. **scm**. azurewebsites.net)로 이동 **사이트 확장**합니다.
1. 스냅숏 디버거 사이트 확장에 있는 X를 제거 하려면 클릭 합니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio의 디버깅](../debugger/index.md)
- [스냅숏 디버거를 사용 하 여 라이브 ASP.NET 앱 디버그](../debugger/debug-live-azure-applications.md)
- [라이브 ASP.NET Azure 가상 Machines\Virtual Machines Scale Sets 스냅숏 디버거를 사용 하 여 디버그](../debugger/debug-live-azure-virtual-machines.md)
- [스냅숏 디버거를 사용 하 여 라이브 ASP.NET Azure Kubernetes 디버깅](../debugger/debug-live-azure-kubernetes.md)
- [스냅숏 디버깅 문제 해결 및 알려진 문제](../debugger/debug-live-azure-apps-troubleshooting.md)
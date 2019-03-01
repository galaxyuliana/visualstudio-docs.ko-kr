---
title: 동기적으로 자동 로드된 확장
ms.date: 02/16/2019
ms.topic: conceptual
ms.assetid: 822e3cf8-f723-4ff1-8467-e0fb42358a1f
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ad3831fb06d23f622f85a55f5efd0a5650ca5e47
ms.sourcegitcommit: 62149c96de0811415e99bb1e0194e76c320e1a1e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2019
ms.locfileid: "57007165"
---
# <a name="synchronously-autoloaded-extensions"></a>동기적으로 자동 로드된 확장

동기적으로 자동 확장 Visual Studio의 성능에 부정적인 영향을 미치는 고 비동기 autoload를 대신 사용 하도록 변환 해야 합니다. 사용자는 Visual Studio 2019 Preview 2부터 확장 될 때 동기적으로 자동 알림을 받습니다. 확장 로드를 정상적으로 작동 합니다.

![확장 호환성 경고](media/extension-compatibility-warning.png)

사용자는 다음 작업을 수행할 수 있습니다.

- 클릭할 **자세한** 하이 정보 페이지로 이동 합니다.

- 클릭할 **성능 관리** 열려는 합니다 [성능 관리자 대화](#performance-manager-dialog) 확장 및 도구 창을 사용 하 여 성능 문제를 보여 주는 합니다.

- 클릭할 **이 메시지를 다시 표시 안 함** 여 알림을 해제 합니다. 이 옵션을 선택 하면 모든 향후 알림용으로만 동기적으로 자동 확장도 차단 합니다. 사용자는 다른 Visual Studio 기능에 대 한 알림을 계속 됩니다.

### <a name="performance-manager-dialog"></a>성능 관리자 대화 상자

![성능 관리자 대화 상자](media/performance-manager.png)

동기적으로 사용자 세션의 모든 패키지를 로드 하는 모든 확장에 표시 된 **사용 되지 않는 Api** 탭 합니다.

* 사용자가 클릭할 수는 **이 문제에 대 한 자세한 내용은** 사용 되지 않는 Api에 대 한 자세한 정보를 수집 합니다.
* 사용자가 마이그레이션 진행률에 대 한 공급 업체 확장을 요청할 수 있습니다.

확장 작성자가 마이그레이션에 대 한 지침을 찾을 수 있는 비동기 autoload 패키지 [AsyncPackage로 마이그레이션](https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration).

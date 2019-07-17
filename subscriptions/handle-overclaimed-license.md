---
title: 과도하게 요청된 라이선스 처리 | Microsoft Docs
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 02/13/2018
ms.topic: conceptual
description: 관리자가 과도하게 요청된 구독을 해결하는 방법에 대해 알아봅니다.
ms.openlocfilehash: 23a0888a670c10af4447d7a097067ffe4fe70c0f
ms.sourcegitcommit: 208395bc122f8d3dae3f5e5960c42981cc368310
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67783446"
---
# <a name="overallocated-subscriptions"></a>초과 할당된 구독

구독자가 추가된 후 주문자가 변경되어 결국 회사가 소유하는 라이선스보다 더 많은 구독이 할당되는 경우가 간혹 있습니다. 이 경우 구독자 탭에 경고가 표시되며 자세한 정보가 제공됩니다.

> [!NOTE]
> 과도하게 요청된 시나리오는 오픈 라이선스 프로그램에서 허용되지 않습니다.  또한 다른 프로그램이 이 정보를 포털에 다르게 표시할 수 있습니다.
>
> [!div class="mx-imgBorder"]
> ![과도하게 요청된 구독 알림](_img/over-claimed/over-claimed-alert.png)

## <a name="resolving-overallocated-subscriptions"></a>초과 할당된 구독 해결

초과 할당된 라이선스를 해결하려면 다음을 수행합니다.

1. 경고 텍스트를 클릭합니다. 그러면 구독 수준에 할당된 구독자의 필터링된 목록과 과도하게 요청된 만료 날짜가 표시됩니다. 

2. 과도하게 요청된 라이선스를 수정하기 위해 필요한 구독자를 제거합니다. 

3. 페이지의 왼쪽에 있는 개요가 다시 규정은 준수하는 것을 나타내도록 업데이트되고 과도하게 요청됨 알림이 모두 사라집니다. 

## <a name="billing-and-true-up"></a>청구 및 true-up

조직에 EA(기업계약)가 있는 경우 관리자는 구매 없이도 구독을 할당할 수 있고, 나중에 "true up"이라고 알려진 조정 프로세스를 통해 구독료를 지불할 수 있습니다.  초과 할당하면 "true-up" 기간 동안 사용자에게 할당된 최대 구독 수에 대한 비용이 조직에 청구됩니다.  이는 true-up이 이루어질 때 할당된 최대 구독 수가 더 이상 없더라도 마찬가지입니다.  최대 사용량 모니터링에 대한 자세한 내용은 [최대 사용량](maximum-usage.md) 항목을 참조하세요.

> [!Important]
> GitHub Enterprise가 포함된 Visual Studio Subscriptions가 Visual Studio 구독 관리자에 의해 할당되고 해당 구독의 구매가 없는 경우 조직 내의 GitHub Enterprise 관리자에게 해당 항목이 표시되지 않습니다. GitHub Enterprise 구독을 표시하려면 구독을 처음 할당할 때 **하나 이상의** GitHub Enterprise가 포함된 Visual Studio Professional 또는 GitHub Enterprise 구독이 포함된 Visual Studio Enterprise를 구매해야 합니다.  
>
> 할당된 각 GitHub 구독에 대해 관리 포털에 할당된 GitHub 구독이 있는 해당 Visual Studio가 이 구독에 대한 라이선스 요구 사항을 준수하는지 확인하는 것은 고객의 책임입니다.

[GitHub Enterprise가 포함된 Visual Studio 구독](assign-github.md) 관리에 대해 자세히 알아봅니다.

## <a name="support-resources"></a>지원 리소스

- Visual Studio 구독에 대한 판매, 구독, 계정 및 요금 청구에 대한 지원을 받으려면 Visual Studio [구독 지원](https://visualstudio.microsoft.com/subscriptions/support/)에 문의하세요.

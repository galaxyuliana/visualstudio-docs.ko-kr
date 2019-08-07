---
title: 구독 관리 포털 시작하기 | Visual Studio Marketplace
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/24/2019
ms.topic: conceptual
description: 구독 관리 포털을 사용하여 조직의 Visual Studio 구독 관리를 시작하는 방법을 알아봅니다.
ms.openlocfilehash: f3b11a0a0977fff8a6c89f565adffb1cac49e2ad
ms.sourcegitcommit: ce1ab8a25c66a83e60eab80ed8e1596fe66dd85c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2019
ms.locfileid: "68605728"
---
# <a name="get-started-with-the-visual-studio-subscriptions-administration-portal"></a>Visual Studio 구독 관리 포털 시작하기
Visual Studio 구독 관리 포털을 사용하는 경우 다음 사항을 명심하세요.
- **Visual Studio 구독에서는 사용자별로 라이선스가 부여됩니다.** 각 구독자는 개발 및 테스트에 필요한 만큼 여러 컴퓨터에서 소프트웨어를 사용할 수 있습니다.
- 조직에서 구입한 Visual Studio 구독에 해당하는 **각 구독자에 대해 하나의 구독 수준만 할당합니다**. 구독 수준이 둘 이상 할당된 구독자가 있으면 구독 수준이 하나만 있도록 해당 설정을 편집합니다.
- 구독이 업그레이드되거나("버전 업그레이드" 라이선스 구입 후) 더 낮은 수준으로 갱신되는 경우 **구독자의 구독 수준을 업데이트해야 합니다**.
- **구독자 간에 구독을 공유하지 않습니다.** 구독을 명명된 개인에게 할당해야 합니다.  팀에게는 구독 할당이 허용되지 않습니다.  구독 혜택(개발 및 테스트용 소프트웨어, Microsoft Azure, E-Learning 등)의 전부 또는 일부를 사용하는 모든 사용자에게 구독을 할당해야 합니다.

## <a name="access-to-the-portal"></a>포털에 대한 액세스
조직의 계약에 대한 기본 또는 통지 연락처 담당자인 경우 볼륨 라이선싱 계약을 설정할 때 포털에 대한 액세스 권한이 자동으로 프로비전닝됩니다. 시스템 실행 시작 전자 메일을 받게 되며, 포털에 로그인하는 데 사용할 전자 메일 주소가 표시됩니다. 로그인하면 자동으로 고급 관리자로 설정되며 구독 및 다른 관리자에 대한 관리를 시작할 수 있습니다. 

## <a name="administrator-roles"></a>관리자 역할
볼륨 라이선스 고객을 위한 새로운 Visual Studio 구독 관리 포털에는 서로 다른 두 가지 역할이 있습니다. 이러한 역할은 현재 VLSC의 기본/통지 연락처 담당자 역할 및 구독 관리자 역할과 같습니다.

**슈퍼 관리자:** 조직이 처음 설정되면 기본적으로 기본 또는 통지 연락처 담당자가 슈퍼 관리자가 됩니다. 기본 또는 통지 연락처 담당자는 슈퍼 관리자 또는 관리자를 추가로 할당하도록 선택할 수 있습니다. 슈퍼 관리자는 구독자뿐만 아니라 다른 관리자도 추가하거나 제거할 수 있습니다. 시스템에 둘 이상의 슈퍼 관리자가 있는 경우 슈퍼 관리자는 보안을 위해 마지막 두 개를 제외하고 모두 삭제할 수 있습니다.

**관리자:** 관리자는 슈퍼 관리자만 설정할 수 있습니다. 관리자는 슈퍼 관리자가 계약에서 할당한 구독자를 관리할 수 있습니다.

## <a name="the-subscribers-page"></a>구독자 페이지
구독을 할당하면 [구독자] 탭에서 구독자에 대해 다음과 같은 세부 정보가 제공됩니다.
- 각 구독자의 성과 이름
- 해당 사용자에 대한 이메일 주소
- 할당된 구독 수준
- 구독이 할당된 날짜
- 해당 구독에 대한 만료 날짜
- 선택적인 텍스트 설명
- 구독자 다운로드 사용 여부의 표시
- 구독자가 위치한 국가
- 관리 포털에서 할당 통신 전자 메일에 대한 언어 기본 설정
- 통신에 사용되는 로그인 이외의 다른 이메일 주소에 대한 선택적 필드

이 페이지의 왼쪽에는 조직에서 각 계약에 대해 구입하고, 할당하고, 아직 사용 가능한 구독 라이선스의 수에 대한 추가 정보가 표시될 수 있습니다.
> [!div class="mx-imgBorder"]
> ![Visual Studio 구독 관리 포털 구독자 페이지](_img/using-admin-portal/subscribers-page.png)

## <a name="the-details-page"></a>세부 정보 페이지
확인하려는 계약에 대한 자세한 내용을 보려면 [세부 정보] 탭을 선택합니다. 계약 상태, 구입 계정, 조직 세부 정보, 고급 관리자 및 기타 관련 정보를 표시합니다.
> [!div class="mx-imgBorder"]
> ![Visual Studio 구독 관리 포털 세부 정보 페이지](_img/using-admin-portal/details-page.png)

## <a name="next-steps"></a>다음 단계
관리자의 책임에 대해 자세히 알아봅니다.
- [관리자 책임 개요](admin-responsibilities.md)
- [사전 프로덕션 환경 인벤토리](admin-inventory.md)
- [대규모 팀 및 외부 계약업체 관리](manage-teams.md)
- [사용자 할당 추적 및 주문 처리](assignments-orders.md)
- [최대 사용량](maximum-usage.md)으로 구매 커밋 추적

---
title: 마이그레이션 후 Visual Studio 구독 관리 포털에 등록
author: evanwindom
ms.author: jaunger
manager: evelynp
ms.date: 07/12/2018
ms.topic: conceptual
description: 관리 포털로 마이그레이션한 후 Visual Studio 구독에 대한 조직에 성공적으로 등록하는 방법을 알아봅니다.
searchscope: VS Subscription
ms.openlocfilehash: 3b12f5ad2d4f83759c6247f3498eb3da9d376991
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63008267"
---
# <a name="onboard-to-the-visual-studio-subscriptions-administration-portal-after-your-organization-is-migrated"></a>조직이 마이그레이션된 후 Visual Studio 구독 관리 포털에 등록

Microsoft VLSC(볼륨 라이선스 서비스 센터)에서 Visual Studio 구독을 관리했고, 최근에 구독을 관리하기 위해 사이트를 방문한 경우 VLSC에서 더 이상 구독 관리를 사용할 수 없음을 알 것입니다. 구독을 관리하는 프로세스는 다음과 같습니다.
> [!div class="mx-imgBorder"]
> ![구독 탭이 강조 표시된 Microsoft VLSC 스크린샷](_img/post-migration-onboarding/vlsc-subscriptions.png)

그러나 이제 Visual Studio Subscription 관리 포털이라는 새 포털을 통해 구독을 관리합니다. 일반적으로 조직의 볼륨 라이선싱 계약에 대한 주 연락처 또는 통지 연락처가 이 프로세스를 완료합니다. 그러지 않은 경우 다음 정보를 사용하여 구독 관리 권한을 얻을 수 있습니다.

다음과 같은 여러 가지 시나리오 중 하나가 발생할 수 있습니다.

1. [주 연락처가 온보딩 프로세스를 완료하지 않은 경우](#onboarding-not-completed-by-primary-contact)
2. [주 연락처가 온보딩을 완료했지만 사용자를 관리자로 추가하지 않았고 자격 증명이 VLSC에 나열되어 있는 경우](#primary-contact-did-not-provide-you-administrator-access)
3. [주 연락처가 온보딩을 완료했지만 사용자를 관리자로 추가하지 않았고 자격 증명이 VLSC에 나열되지 않은 경우](#your-credentials-were-not-listed-in-vlsc-prior-to-migration)

<sup>1</sup> 사용자가 주 또는 통지 연락처이고 온보딩 프로세스를 완료하지 않은 경우에는 조직을 설정하기 위해 시나리오 1의 단계를 수행해야 합니다.

다음 섹션에서는 이러한 각 시나리오에 대해 자세히 설명합니다.

## <a name="onboarding-not-completed-by-primary-contact"></a>주 연락처가 온보딩을 완료하지 않은 경우

주 연락처가 온보딩 환경을 완료하지 않은 경우 다음 화면이 표시됩니다. [VLSC(볼륨 라이선스 서비스 센터)](https://www.microsoft.com/Licensing/servicecenter/default.aspx)에 액세스할 수 있는 경우 이 프로세스를 완료하고 구독을 관리할 권한을 얻을 수 있습니다. VLSC에서 찾을 수 있는 조직의 [PCN(공용 고객 번호)](find-pcn.md)이 필요합니다.

PCN 필드에 [PCN](find-pcn.md)을 입력하고 **초대 전자 메일 보내기**를 선택합니다.
> [!div class="mx-imgBorder"]
> ![Visual Studio 구독 관리 포털 스크린샷](_img/post-migration-onboarding/send-invitation.png)

온보딩 프로세스를 완료하기 위한 고유한 링크가 포함된 전자 메일을 받게 됩니다. 전자 메일에서 링크를 클릭하고, 전자 메일 주소로 로그인한 후, 다시 한번 PCN을 입력합니다. 전자 메일의 고유한 링크를 통해 Visual Studio Subscription 관리 포털에 대한 액세스 권한을 얻을 수 있습니다. 그런 다음, 구독에 액세스하고 관리할 수 있습니다.
> [!div class="mx-imgBorder"]
> ![성공 알림 스크린샷](_img/post-migration-onboarding/email-success.png)

## <a name="primary-contact-did-not-provide-you-administrator-access"></a>주 연락처가 관리자 액세스 권한을 제공하지 않은 경우

주 연락처가 온보딩 프로세스를 완료했고 이전에 VLSC에 자격 증명이 있었지만 주 연락처가 액세스 권한을 제공하지 않은 경우 다음 알림이 표시됩니다. 관리자가 되려면 알림에 나열된 조직의 슈퍼 관리자 중 한 명에게 문의합니다.
> [!div class="mx-imgBorder"]
> ![슈퍼 관리자 목록이 표시된 Visual Studio 구독 관리 포털 스크린샷](_img/post-migration-onboarding/admin-list.png)

## <a name="your-credentials-were-not-listed-in-vlsc-prior-to-migration"></a>마이그레이션하기 전에 자격 증명이 VLSC에 나열되지 않은 경우

주 연락처가 온보딩을 완료했지만 사용자로 추가하지 않았고 자격 증명이 이전에 VLSC에 나열되지 않은 경우 다음 알림이 표시됩니다. 포털에 대한 액세스 권한을 얻으려면 [주 연락처](find-primary-contact.md)에게 연락합니다.
> [!div class="mx-imgBorder"]
> ![“사용자를 찾을 수 없음” 알림이 표시된 Visual Studio 구독 관리 포털 스크린샷](_img/post-migration-onboarding/cant-find-you.png)
---
title: Visual Studio 구독자 데이터의 익명화 | Microsoft Docs
author: evanwindom
ms.author: lank
manager: lank
ms.date: 07/19/2019
ms.topic: conceptual
description: 구독에 대한 액세스 권한이 중단된 경우 구독자 데이터가 익명화되는 방법을 알아봅니다.
ms.openlocfilehash: 8ba1a462083281c2228f2d6e25c42485ead8aa19
ms.sourcegitcommit: 485881e6ba872c7b28a7b17ceaede845e5bea4fe
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/22/2019
ms.locfileid: "68377967"
---
# <a name="anonymization-of-visual-studio-subscriber-information"></a>Visual Studio 구독자 정보의 익명화
구독 만료 또는 구독자 로그인 계정 삭제와 같은 구독자의 구독 사용을 차단하는 이벤트가 발생하면, 이름 및 로그인 계정과 같은 사용자의 개인 정보는 기본적으로 사용할 수 없도록 하기 위해 암호화됩니다.  이는 구독자의 개인 정보를 보호하기 위해 수행됩니다.

[!INCLUDE [GDPR-related guidance](includes/gdpr-intro-sentence.md)]

## <a name="when-does-anonymization-occur"></a>익명화는 언제 발생하나요?
구독자에게 구독을 사용할 수 없게 렌더링하는 이벤트는 익명화를 트리거합니다.  익명화가 얼마나 빠르게 발생하는지는 구독 유형 및 트리거 이벤트에 따라 다릅니다. 자세한 내용은 아래 표를 참조하세요.

| 구독 유형                                                                                                                       | 익명화를 트리거하는 이벤트                                                                                                     | 익명화 발생 시 |
|-----------------------------------------------------------------------------------------------------------------------------------------|------------------------------------------------------------------------------------------------------------|---------------------------|
| Visual Studio Dev Essentials                                                                                                            | 구독자가 프로그램을 옵트아웃하거나 사용 약관에 동의하지 않음                                    | 30일               |
| Microsoft Store를 통해 구입한 Visual Studio 구독(일반 정품)                                                                      | 구독이 만료되거나 활성화되지 않았습니다.                                                                   | 360일                  |
| Volume License, Visual Studio Marketplace(클라우드 구독) 또는 MPN과 같은 프로그램을 통해 구입한 Visual Studio 구독 | 구독이 만료되거나 사용자에게 할당되지 않았습니다.                                                          | 180일                  |
| 모든 구독                                                                                                                       | 구독에 로그인하는 데 사용되는 Azure Active Directory 계정 또는 Microsoft 계정(MSA)이 닫힙니다. | 즉시               |
| 모든 구독                                                                                                                       | Azure Active Directory 계정과 연결된 테넌트에서 제거되었습니다.                                | 즉시               |

## <a name="faq"></a>FAQ
### <a name="q--does-the-anonymization-of-the-subscribers-personal-information-cause-them-to-lose-access-to-the-subscription"></a>Q:  구독자의 개인 정보가 익명화되어 구독에 대한 액세스 권한이 손실되었나요?
A:  아니요.  익명화는 구독에 대한 액세스 권한의 손실을 유발하지만 액세스 부족이 발생하지 않는 이벤트에 대한 응답입니다.

### <a name="q--im-an-administrator-for-my-organizations-subscriptions--if-one-of-my-subscribers-information-is-anonymized-can-that-subscription-be-reassigned-to-another-user"></a>Q:  내 조직의 구독에 대한 관리자입니다.  구독자의 정보 중 하나가 익명으로 되어 있으면 해당 구독을 다른 사용자에게 다시 할당할 수 있나요?
A:  예 -- 구독이 만료되지 않는 한 다른 구독자에게 다시 할당할 수 있습니다.

## <a name="next-steps"></a>다음 단계
[MSA 및 AAD ID를 연결](/azure/active-directory/b2b/add-users-administrator)하여 익명화를 방지하는 방법을 알아봅니다.

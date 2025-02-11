---
title: 부하 테스트에 대한 브라우저 테스트 조합
ms.date: 10/19/2016
ms.topic: conceptual
helpviewer_keywords:
- load tests, web browser types
- load tests, scenarios
- load tests, adding browsers
- load tests, removing browsers
ms.assetid: 47f981d9-3038-45cc-a486-82b9daf9a9a1
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 6694b850c7fee73e4b0891d37891e44a85f142f2
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68918248"
---
# <a name="edit-the-test-mix-to-specify-which-web-browsers-types-in-a-load-test-scenario"></a>테스트 조합을 편집하여 부하 테스트 시나리오의 웹 브라우저 형식 지정

*브라우저 조합*을 통해 부하 테스트 시나리오에서 부하를 보다 사실적으로 시뮬레이션할 수 있습니다. 이 경우 단일 웹 브라우저가 아니라 서로 다른 종류의 웹 브라우저로 구성된 조합을 사용하여 부하가 생성됩니다. 따라서 애플리케이션과 함께 사용될 웹 브라우저를 보다 정확하게 테스트할 수 있습니다.

브라우저 조합에서는 부하 테스트 시나리오에서 가상 사용자가 특정 웹 브라우저 종류를 실행할 가능성을 지정합니다. 부하 테스트를 만들 때 둘 이상의 웹 브라우저를 통해 부하가 생성되도록 시뮬레이트할 수 있습니다. 제공된 웹 브라우저 집합의 웹 브라우저 종류를 조합에 추가하면 선택한 웹 브라우저에 대한 관련 헤더 집합이 웹 성능 테스트 시 전송되는 각 HTTP 요청에 추가됩니다.

브라우저 조합은 다른 목록 옵션과 마찬가지로 작동합니다. 웹 브라우저 종류는 브라우저 조합을 기반으로 가상 사용자와 임의로 연결됩니다. 해당 사용자의 테스트는 조합에 지정된 가능성에 따라 특정 웹 브라우저에서 실행됩니다.

브라우저 조합을 지정한 후 필요에 따라 나중에 웹 브라우저 종류를 조합에 추가하고 제거할 수 있습니다. 목록 컨트롤을 사용하여 브라우저 조합의 분포를 변경할 수도 있습니다. 목록 컨트롤을 통해 시나리오의 브라우저 분포를 쉽게 조정할 수 있습니다.

[!INCLUDE [web-load-test-deprecated](includes/web-load-test-deprecated.md)]

## <a name="add-new-browsers-to-a-scenario"></a>시나리오에 새 브라우저 추가

### <a name="to-add-new-browsers-to-a-scenario"></a>시나리오에 새 브라우저를 추가하려면

1. 시나리오의 브라우저 조합을 지정하는 단계에서 **추가**를 선택합니다.

     표에 새 브라우저 항목이 추가됩니다.

    > [!NOTE]
    > **브라우저 조합 편집** 대화 상자를 표시하려면 기존 시나리오를 마우스 오른쪽 단추로 클릭한 다음, **브라우저 조합 편집**을 선택합니다.

2. **브라우저 형식** 열에서 새 항목에 대한 화살표 단추를 선택하고 원하는 브라우저 형식을 선택합니다.

3. (선택 사항) 목록 컨트롤을 조정하여 테스트 분포를 조정합니다.

4. 브라우저 추가를 마쳤으면 **확인**을 선택합니다.

## <a name="remove-browsers-from-a-scenario"></a>시나리오에서 브라우저 제거

### <a name="to-remove-browsers-from-a-scenario"></a>시나리오에서 브라우저를 제거하려면

1. 부하 테스트를 엽니다.

2. 브라우저를 제거할 시나리오를 마우스 오른쪽 단추로 클릭하고 **브라우저 조합 편집**을 선택합니다.

     **브라우저 조합 편집** 대화 상자가 표시됩니다.

3. 눈금에서 브라우저를 선택한 다음, **제거**를 선택합니다.

4. (선택 사항) 목록 컨트롤을 조정하여 테스트 분포를 조정합니다.

5. 브라우저 제거를 마쳤으면 **확인**을 선택합니다.

## <a name="about-the-mix-control"></a>조합 제어 정보

목록 컨트롤을 사용하면 부하 테스트 시나리오에서 여러 테스트, 브라우저 종류 또는 네트워크 형식 간에 부하가 분산되는 백분율을 조정할 수 있습니다. 슬라이더를 움직이면 백분율 값이 조정됩니다. 브라우저 형식에 대한 조합을 조정하면 부하 테스트 시나리오에서 가상 사용자가 특정 브라우저 프로필을 실행할 가능성이 지정됩니다.

슬라이더를 움직이면 사용 가능한 모든 항목의 백분율 값이 변경됩니다. 항목이 셋 이상인 경우 더하거나 빼는 양이 다른 항목에 고르게 분산됩니다. 이 동작을 재정의할 수도 있습니다. 특정 값 항목의 잠금 열에 있는 확인란을 선택하면 해당 항목에 지정된 백분율 값이 잠깁니다. 이렇게 하면 슬라이더를 움직일 때 더하거나 빼는 양이 잠기지 않은 항목에만 적용됩니다.

**균등 맞춤** 단추는 모든 항목 간에 백분율 값을 균등하게 할당하는데 사용됩니다. 예를 들어 항목이 세 개인 경우, **균등 맞춤**을 선택하면 백분율 값이 34, 33 및 33으로 설정됩니다.

> [!WARNING]
> **균등 맞춤** 단추는 잠긴 모든 항목을 재정의합니다.

슬라이더를 사용하는 대신 백분율 값을 직접 **%** 열에 입력할 수도 있습니다. 백분율 값을 직접 입력하는 경우에는 다른 항목이 자동으로 조정되지 않습니다.

> [!NOTE]
> 합계가 100%가 되지 않거나 **%** 열에 입력된 백분율 값이 소수일 경우 슬라이더는 비활성화됩니다.

백분율 값을 직접 입력할 때는 모든 항목을 더한 값이 100%인지 확인해야 합니다. 목록을 저장할 때 합계가 100%가 아니면 현재 백분율을 그대로 사용할지 또는 이전 단계로 돌아가서 백분율 값을 조정할지 선택하라는 메시지가 표시됩니다. 현재 백분율을 그대로 사용하도록 선택하면 각 값이 100%를 기준으로 조정됩니다.  예를 들어 두 개의 항목이 있고 두 항목의 값을 80%와 40%로 직접 설정한 경우 첫 번째 항목은 80을 120으로 나눈 값인 66.67%로, 두 번째 항목은 40을 120으로 나눈 값인 33.33%로 설정됩니다.

## <a name="see-also"></a>참고 항목

- [부하 테스트 시나리오 편집](../test/edit-load-test-scenarios.md)
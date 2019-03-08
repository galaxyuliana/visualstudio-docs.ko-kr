---
title: 분해자 생성 빠른 작업
ms.date: 02/19/2019
ms.topic: reference
author: kendrahavens
ms.author: kendrahavens
manager: jillfra
dev_langs:
- CSharp
ms.workload:
- dotnet
ms.openlocfilehash: a609b16e0d1bc7e30dc26ef047228a6cacdb46b2
ms.sourcegitcommit: 11337745c1aaef450fd33e150664656d45fe5bc5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/04/2019
ms.locfileid: "57324738"
---
# <a name="generate-a-deconstructor-in-visual-studio"></a>Visual Studio에서 분해자 생성

이 코드 생성은 다음에 적용됩니다.

- C#

**내용:** 새 분해자에 대한 메서드 스텁을 즉시 생성할 수 있습니다.

**시기:** 제대로 형식을 자동으로 분해하려고 합니다.

**이유:** 수동으로 분해자를 입력할 수 있지만 이 기능은 올바른 out 매개 변수로 스텁을 생성합니다.

## <a name="generate-deconstructor"></a>분해자 생성

1. 원하는 out 매개 변수를 지정하여 새로운 형식을 선언합니다. 이 선언은 선언과 일치하는 분해 인스턴스를 찾을 수 없을 때 오류가 발생됩니다.

   ![분해자 오류 누락](media/deconstruct.png)

2. 다음으로, 다음 중 하나를 수행합니다.

   - **키보드**
      - 선언에 커서를 사용하여 **Ctrl**+**를 누룹니다.** **빠른 작업 및 리팩터링** 메뉴를 트리거합니다.
   - **마우스**
      - 마우스 오른쪽 단추로 클릭하고 **빠른 작업 및 리팩터링** 메뉴를 선택합니다.
      - 텍스트 커서가 이미 구부러진 빨간 곡선이 있는 줄 위에 있으면 왼쪽 여백에 나타나는 ![스크루드라이버](media/screwdriver.png) 아이콘을 클릭합니다.

      ![분해자 codefix 생성](media/deconstruct-codefix.png)

3. **'MyInternalClass.Deconstruct' 메서드 생성**을 선택하여 분해자를 생성합니다.

   ![결과 분해자 코드](media/deconstruct-result.png)


## <a name="see-also"></a>참고 항목

- [코드 생성](../code-generation-in-visual-studio.md)
- [변경 내용 미리 보기](../../ide/preview-changes.md)
- [.NET 개발자를 위한 팁](../../ide/visual-studio-2017-for-dotnet-developers.md)
---
author: dotpaul
ms.author: paulming
ms.date: 04/05/2019
ms.topic: include
ms.openlocfilehash: 43327901b2233b9b2818296f9269975d8524438b
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62541566"
---
안전 하지 않은 deserializers는 신뢰할 수 없는 데이터를 역직렬화 하는 동안에 취약 합니다. 공격자는 악의적인 의도 사용 하 여 예기치 않은 형식이 serialize 된 데이터를 수정할 수 있습니다. 안전 하지 않은 역직렬 변환기가 공격 수, 예를 들어, 기본 운영 체제에서 명령을 실행, 네트워크를 통해 통신 또는 파일을 삭제 합니다.
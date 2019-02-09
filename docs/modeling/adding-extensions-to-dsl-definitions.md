---
title: DSL 정의에 확장 추가
ms.date: 11/04/2016
ms.topic: conceptual
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: ec4be7c084bbcd1a73affa3035f1ef116d958c9a
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55909625"
---
# <a name="add-extensions-to-dsl-definitions"></a>DSL 정의에 확장 추가

DSL 정의 확장을 사용 하면 도메인 특정 언어 (DSL)에 대 한 확장의 패키지를 만들 수 있습니다. 에 VSIX Visual Studio Integration Extension ()에 포함 되는 DSL 확장을 동일한 방식으로 DSL에서 사용자의 컴퓨터에 설치할 수 있습니다. 추가 기능 동적으로 사용 하도록 설정 하 고 런타임 시 사용 하지 않도록 설정 될 수 있습니다. Dsl 확장에 대 한 명시적으로 디자인할 수 없고 확장 디자인할 수 있습니다 나중 또는 제 3 자에서 확장 된 DSL을 변경 하지 않고 있습니다.

DSL 확장 같은 기능을 포함할 수 있습니다.

-   모델 및 프레젠테이션 요소에 대 한 속성

-   모양 및 연결선에 대 한 decorator

-   클래스, 관계, 모양 및 연결선

-   유효성 검사 제약 조건

-   도구 상자 항목 및 탭

확장된을 사용 하는 DSL의 사용자를 만들고 추가 기능은 인스턴스를 포함 하는 모델을 저장할 수 있습니다. 적절 한 확장명 설치 되어 있는 다른 사용자가 모델을 읽을 수 있습니다. 확장을 설치 하지 않은 사용자는 추가 기능을 사용할 수 없습니다 하지만 업데이트 하 고 추가 기능을 손실 하지 않고 모델을 저장할 수 있습니다.

[!INCLUDE[modeling_sdk_info](includes/modeling_sdk_info.md)]

## <a name="see-also"></a>참고 항목

- [관련된 블로그 게시물](https://blogs.msdn.microsoft.com/visualstudioalm/tag/code-index/)

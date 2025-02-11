---
title: 'DA0022: Gen 2 가비지 수집의 비율이 높습니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.DA0022
- vs.performance.rules.DA0022
- vs.performance.22
ms.assetid: f871a547-0e6f-4b11-b2d7-174d30fc2ed8
caps.latest.revision: 13
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 820d74a9dced29dc237c4bf182419abcb7d503b3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194920"
---
# <a name="da0022-high-rate-of-gen-2-garbage-collections"></a>DA0022: Gen 2 가비지 수집의 비율이 높습니다.
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

규칙 Id | DA0022 |  
| 범주. NET Framework 사용 |  
| 프로 파일링 방법을 | 모든 |  
| 메시지 | Gen 2 가비지 수집의 비율이 상당히 높습니다 있습니다. 의도적으로 프로그램의 데이터 구조가 대다수 오랜 시간 동안 할당되고 지속되는 경우 일반적으로 이러한 현상은 문제가 되지 않습니다. 하지만 이러한 동작이 의도되지 않은 경우에는 애플리케이션이 개체를 고정하고 있는 것일 수 있습니다. 확실하지 않으면 .NET 메모리 할당 데이터 및 개체 수명 정보를 수집하여 애플리케이션이 사용하는 메모리 할당 패턴을 파악할 수 있습니다.|  
| 규칙 유형 | 경고 |  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링할 경우 이 규칙을 트리거하려면 10개 이상의 샘플을 수집해야 합니다.  
  
## <a name="cause"></a>원인  
 프로파일링 중에 수집된 시스템 성능 데이터는 0세대 및 1세대 가비지 수집에 비해 .NET Framework 개체용 메모리의 상당한 부분이 가비지 수집의 2세대에서 회수되었음을 나타냅니다.  
  
## <a name="rule-description"></a>규칙 설명  
 Microsoft .NET CLR(공용 언어 런타임)는 가비지 수집을 사용하여 애플리케이션에 더 이상 사용되지 않는 개체에서 메모리를 회수하는 자동 메모리 관리 메커니즘을 제공합니다. 가비지 수집기는 많은 할당이 단기 유지된다는 가정 하에 세대를 기준으로 합니다. 예를 들어 로컬 변수는 단기 유지되어야 합니다. 새로 만들어진 개체는 0세대(gen 0)에서 시작되고, 가비지 수집 실행에서 생존하면 1세대로 이동하고, 애플리케이션에 계속 사용될 경우 마지막으로 2세대로 전환됩니다.  
  
 0세대의 개체는 빈번하게, 보통 매우 효율적으로 수집됩니다. 1세대의 개체는 덜 빈번하게, 덜 효율적으로 수집됩니다. 마지막으로 2세대의 장기 유지 개체는 훨씬 덜 빈번하게 수집되어야 합니다. 전체 가비지 수집 실행을 나타내는 2세대 수집은 가장 부담이 큰 작업이기도 합니다.  
  
 비교적 너무 많은 2세대 수집이 발생한 경우 이 규칙이 실행됩니다. 정상 작동하는 .NET Framework 애플리케이션에는 1세대 수집이 2세대 수집보다 6배 이상 많이 포함됩니다. 10배 요소가 이상적일 것입니다.  
  
## <a name="how-to-investigate-a-warning"></a>경고를 조사하는 방법  
 [오류 목록] 창에서 메시지를 두 번 클릭하여 프로파일링 데이터의 [표시 뷰](../profiling/marks-view.md)로 이동합니다. **.NET CLR Memory\\# of Gen 0 Collections** 및 **.NET CLR Memory\\# of Gen 1 Collections** 열을 찾습니다. 가비지 수집이 더 빈번히 발생하는 특정 프로그램 실행 단계가 있는지 확인합니다. 이러한 값을 **% Time in GC** 열에 비교하여 관리되는 메모리 할당의 패턴이 과도한 메모리 관리 오버헤드를 일으키는지 확인합니다.  
  
 높은 비율의 2세대 가비지 수집이 항상 문제가 되는 것은 아닙니다. 정상적인 현상일 수 있습니다. 실행 중에 장기간 활성 상태를 유지해야 하는 큰 데이터 구조를 할당하는 애플리케이션이 이 규칙을 트리거할 수 있습니다. 이런 애플리케이션에 메모리가 부족한 경우 빈번한 가비지 수집이 강제로 수행될 수 있습니다. 부담이 적은 0세대 및 1세대 가비지 수집이 관리되는 메모리를 적은 양만 회수할 수 있는 경우에는 더 빈번한 2세대 가비지 수집이 예약됩니다.  
  
 표시 뷰에는 가비지 수집 문제를 확인하도록 도울 수 있는 추가적인 .NET CLR Memory 열이 있습니다. **% Time in GC** 열을 통해 발생하는 메모리 관리 오버헤드의 양을 파악할 수 있습니다. 애플리케이션이 크지만 영구적인 개체를 상당히 적게 사용할 경우 빈번한 2세대 수집이 과도한 CPU 시간을 사용하면 안 됩니다. 더 많은 실제 메모리(RAM)가 필요하기 때문에 애플리케이션에 메모리가 부족할 경우 **Memory\Pages/sec** 열 값을 평가하는 관련 규칙도 실행될 수 있습니다.  
  
 애플리케이션의 관리되는 메모리 사용 패턴을 파악하려면 .NET 메모리 할당 프로필을 실행하여 애플리케이션을 다시 프로파일링하고 개체 수명 프로파일링 옵션을 선택합니다.  
  
 가비지 수집 성능 향상 방법에 대한 자세한 내용은 Microsoft 웹 사이트에서 [가비지 수집기 기본 및 성능 힌트](http://go.microsoft.com/fwlink/?LinkId=148226)를 참조하세요. 자동 가비지 수집의 오버헤드에 대한 자세한 내용은 [Large Object Heap Uncovered](http://go.microsoft.com/fwlink/?LinkId=177836)(대형 개체 힙 살펴보기)를 참조하세요.

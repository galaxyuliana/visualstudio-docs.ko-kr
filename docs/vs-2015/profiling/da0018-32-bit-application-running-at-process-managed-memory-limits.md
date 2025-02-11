---
title: 'DA0018: 프로세스 관리 메모리 한도로 실행 중인 32비트 애플리케이션 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.18
- vs.performance.DA0018
- vs.performance.rules.DA0018
ms.assetid: 98eb2d96-f92f-42f9-915c-e5ac2330ffbf
caps.latest.revision: 14
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 6418a39d7e53a3edaa48b3cd003d35d95cba386e
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68194953"
---
# <a name="da0018-32-bit-application-running-at-process-managed-memory-limits"></a>DA0018: 프로세스 관리되는 메모리 한도로 실행 중인 32비트 애플리케이션
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

규칙 Id | DA0018 |  
| 범주 | 프로 파일링 도구 사용 |  
| 프로 파일링 방법을 | 샘플링 |  
| 메시지 | 32 비트 프로세스에 대 한 기본 제한에 도달 하는 메모리 할당을 관리 합니다. 애플리케이션이 메모리 바인딩될 수 있습니다.|  
| 규칙 유형 | 경고 |  
  
 샘플링, .NET 메모리 또는 리소스 경합 방법을 사용하여 프로파일링할 경우 이 규칙을 트리거하려면 10개 이상의 샘플을 수집해야 합니다.  
  
## <a name="cause"></a>원인  
 프로파일링 실행 동안 수집된 시스템 데이터가 .NET Framework 메모리 힙이 32비트 프로세스에서 관리되는 힙이 도달할 수 있는 최대 크기에 도달했음을 나타냅니다. 이 최대 크기가 기본값입니다. 이 크기는 전용 바이트에 할당될 수 있는 프로세스 주소 공간의 전체 크기를 기초로 합니다. 보고된 값은 프로파일링된 프로세스가 활성화된 동안 관찰된 힙의 최대값입니다. .NET 메모리 프로파일링 방법을 사용하고 애플리케이션의 관리되는 리소스 사용을 최적화하여 다시 프로파일링해 보세요.  
  
 관리되는 힙 크기가 기본 한도에 도달하면 자동 가비지 수집 프로세스를 더 빈번히 호출해야 할 수 있습니다. 이로 인해 메모리 관리의 오버헤드가 증가합니다.  
  
 규칙은 32비트 컴퓨터에서 실행되는 32비트 애플리케이션에 대해서만 실행됩니다.  
  
## <a name="rule-description"></a>규칙 설명  
 Microsoft .NET CLR(공용 언어 런타임)는 가비지 수집을 사용하여 애플리케이션에 더 이상 사용되지 않는 개체에서 메모리를 회수하는 자동 메모리 관리 메커니즘을 제공합니다. 가비지 수집기는 많은 할당이 단기 유지된다는 가정 하에 세대를 기준으로 합니다. 예를 들어 로컬 변수는 단기 유지되어야 합니다. 새로 만들어진 개체는 0세대(gen 0)에서 시작되고, 가비지 수집 실행에서 생존하면 1세대로 이동하고, 애플리케이션에 계속 사용될 경우 마지막으로 2세대로 전환됩니다.  
  
 85KB를 초과하는 관리되는 개체는 큰 개체 힙에 할당되며, 여기에서 이러한 개체는 작은 개체들보다 가비지 수집 및 압축이 덜 수행됩니다. 큰 개체는 보다 지속적인 것으로 간주될 뿐만 아니라, 지속적인 대형 개체를 자주 할당되는 작은 개체와 함께 관리하면 힙이 최악의 상태로 단편화될 수 있으므로 별도로 관리됩니다.  
  
 관리되는 힙의 전체 크기가 기본 한도에 도달하면, 메모리 관리의 오버헤드가 증가하여 애플리케이션의 응답성과 확장성에 영향을 주기 시작합니다.  
  
## <a name="how-to-investigate-a-warning"></a>경고를 조사하는 방법  
 [오류 목록] 창에서 메시지를 두 번 클릭하여 [표시](../profiling/marks-view.md) 뷰로 이동합니다. **.NET CLR Memory\\# Bytes in all Heaps** 및 **# Total committed bytes** 열을 찾습니다. 다른 단계보다 관리되는 메모리 활동이 더 빈번한 특정 프로그램 실행 단계가 있는지 확인합니다. **# Bytes in all Heaps** 열 값을 **.NET CLR Memory\\# of Gen 0 Collections**, **.NET CLR Memory\\# of Gen 1 Collections** 및 **.NET CLR Memory\\# of Gen 2 Collections** 열에서 보고된 가비지 수집 비율에 비교하여 관리되는 메모리 할당의 패턴이 가비지 수집 비율에 영향을 미치는지 확인합니다.  
  
 .NET Framework 애플리케이션에서 공용 언어 런타임은 관리되는 힙의 전체 크기를 프로세스 주소 공간의 최대 전용 영역 크기의 절반보다 약간 작은 크기로 제한합니다. 32비트 컴퓨터에서 실행되는 32비트 프로세스의 경우 프로세스 주소 공간 중 전용 부분의 상한은 2GB입니다. 관리되는 힙의 전체 크기가 기본 한도에 도달하면 관리 메모리의 오버헤드가 증가할 수 있고 애플리케이션 성능이 저하될 수 있습니다.  
  
 관리되는 메모리의 과도한 오버헤드가 문제인 경우 다음 옵션 중 하나를 고려하세요.  
  
- 애플리케이션의 관리되는 메모리 리소스 사용 최적화  
  
   또는  
  
- 32비트 프로세스의 최대 가상 메모리 크기에 대한 아키텍처 제약 조건을 완화하는 단계 수행  
  
  애플리케이션의 관리되는 메모리 리소스 사용을 최적화하려면 .NET 메모리 할당 프로파일링 실행에서 관리되는 메모리 할당 데이터를 수집합니다. [.NET 메모리 데이터 뷰](../profiling/dotnet-memory-data-views.md) 보고서를 검토하여 응용 프로그램의 메모리 할당 패턴을 파악합니다.  
  
  [개체 수명 뷰](../profiling/object-lifetime-view.md)를 사용하여 프로그램의 어떤 데이터 개체가 세대로 생존하고 세대에서 회수되는지 확인합니다.  
  
  [할당 뷰](../profiling/dotnet-memory-allocations-view.md)를 사용하여 이러한 할당이 시작된 실행 경로를 확인합니다.  
  
  가비지 수집 성능을 향상시키는 방법에 대한 자세한 내용은 MSDN 웹 사이트에서 .NET Framework 기술 문서, [가비지 수집기 기본 및 성능 힌트](http://go.microsoft.com/fwlink/?LinkId=177946)를 참조하세요.  
  
  프로세스 주소 공간 중 전용 부분 크기에 대한 가상 메모리 제약 조건을 구조적으로 완화하려면 64비트 컴퓨터에서 이 32비트 프로세스를 실행해 보세요.  64비트 컴퓨터에서 32비트 프로세스를 실행하면 전용 가상 메모리를 4GB까지 확보할 수 있습니다.  
  
  64비트 컴퓨터에서 64비트 프로세스를 실행하면 가상 메모리를 8TB까지 확보할 수 있습니다. 네이티브 64비트 애플리케이션으로 실행되도록 애플리케이션을 다시 컴파일해 보세요. 이 규칙은 참고용으로만 제공되며 정정 작업이 필요하지 않습니다.

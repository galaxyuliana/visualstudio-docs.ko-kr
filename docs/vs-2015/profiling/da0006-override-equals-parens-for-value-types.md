---
title: 'DA0006: 값 형식에 대해 Equals() 재정의 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.performance.rules.DAOverrideEquals
- vs.performance.6
- vs.performance.DA0006
- vs.performance.rules.DA0006
ms.assetid: 4d85bdd6-b571-47e0-afd6-ba3764e4eed5
caps.latest.revision: 17
author: MikeJo5000
ms.author: mikejo
manager: jillfra
ms.openlocfilehash: 2229edad7ff338251fea23740343e23f87aa2792
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "68158675"
---
# <a name="da0006-override-equals-for-value-types"></a>DA0006: 값 형식에 대해 Equals() 재정의
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

규칙 Id | DA0006 |  
| 범주. NET Framework 사용 |  
| 프로 파일링 방법 | 샘플링 |  
| 메시지 | Equals 및 값 형식의 같음 연산자를 재정의 합니다. |  
| 메시지 형식 | 경고 |  
  
## <a name="cause"></a>원인  
 Equals 메서드 또는 공개 값 형식의 같음 연산자에 대한 호출이 프로파일링 데이터의 상당한 부분을 차지합니다. 더 효율적인 메서드를 구현해 보세요.  
  
## <a name="rule-description"></a>규칙 설명  
 값 형식의 경우 Equals의 상속된 구현에서 <xref:System.Reflection> 라이브러리를 사용하며 형식에서 모든 필드의 내용을 비교합니다. Reflection에는 많은 계산이 요구되며 모든 필드의 일치 여부를 비교하는 것이 불필요할 수 있습니다. 사용자가 인스턴스를 비교 또는 정렬하거나 인스턴스를 해시 테이블 키로 사용할 것으로 예측되는 경우에는 값 형식에서 Equals를 구현해야 합니다. 프로그래밍 언어가 연산자 오버로드를 지원하는 경우 같음 및 같지 않음 연산자의 구현도 제공해야 합니다.  
  
 Equals 및 같음 연산자를 재정의하는 방법에 대한 자세한 내용은 [Equals 및 같음 연산자(==) 구현 지침](http://go.microsoft.com/fwlink/?LinkId=177818)을 참조하세요.  
  
## <a name="how-to-investigate-a-warning"></a>경고를 조사하는 방법  
 Equals 및 같음 연산자 구현의 예는 코드 분석 규칙 [CA1815: 값 형식에서 Equals 또는 같음 연산자 재정의](../code-quality/ca1815-override-equals-and-operator-equals-on-value-types.md)를 참조하세요.

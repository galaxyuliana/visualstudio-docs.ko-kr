---
title: 기호 공급자 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- symbol handler
- debugging [Debugging SDK], symbol handler
ms.assetid: 5fce651b-fead-4418-81b0-a011df7644ab
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ed25959cd6afa7232555757e358a99836d93924b
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54981482"
---
# <a name="symbol-provider"></a>기호 공급자
식 계산기 구현 변수와 식을 평가 하기 위해 언어 컴파일러에서 생성 된 기호화 된 디버그 정보에 액세스 해야 합니다. 기호 처리기 라고도 기호 공급자 (SP)의 인터페이스를 사용 하 여 수행 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 프로그램 데이터베이스 (PDB) 기호 파일 형식을 사용 하 여 네이티브 코드 뿐만 아니라 관리 코드에 대 한 SPs를 제공 합니다. 사용자 지정 형식으로 저장 하는 기호를 사용 하기 위해 프로그램에 필요한, 것이 없는 강력한 제공한 SPs를 사용 하는 것이 좋습니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
## <a name="implementation-notes"></a>구현 참고 사항  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 공용 언어 런타임 (CLR) 인터페이스를 사용 하 여 SPs를 사용 하 여 이야기 하고자 하는 디버그 엔진입니다. 결과적으로, Visual Studio 디버그 엔진을 사용 하는 SP CLR을 지원 해야 합니다. 모든 CLR 디버깅 인터페이스의 전체 목록은 일부인 debugref.doc에서 찾을 수 있습니다의 [!INCLUDE[winsdklong](../../deployment/includes/winsdklong_md.md)]합니다.  
  
 에 SP, 사용자 지정 디버그 엔진에만 수행 하는 경우에 디버그 엔진의 요구에 따라 하다 면 SP를 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)
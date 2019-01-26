---
title: IntelliSense 호스팅 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - IntelliSense hosting
ms.assetid: 20c61f8a-d32d-47e2-9c67-bf721e2cbead
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8cf55e2cf88b8cf6f92145ea7a75aa35a5f56486
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958591"
---
# <a name="intellisense-hosting"></a>IntelliSense 호스팅
Visual Studio IntelliSense 호스팅 수 있습니다. Visual Studio 텍스트 편집기에서 호스트 되지 않는 코드에 대 한 IntelliSense를 제공 하면 IntellSense 있습니다 호스팅.  
  
## <a name="intellisense-hosting-usage"></a>IntelliSense 호스팅 사용  
 Visual Studio에서 코드 완성 집합 및 텍스트 버퍼에 대 한 액세스는 가져올 수 있습니다 IntelliSense windows 어디에서 나 사용자 인터페이스 (UI)에 있습니다. 이 몇 가지 예제 시나리오는에서 완료 합니다 **조사식** 창 또는 조건 필드 중단점 속성 창.  
  
### <a name="implementation-interfaces"></a>인터페이스 구현  
  
#### <a name="ivsintellisensehost"></a>IVsIntellisenseHost  
 IntelliSense 팝업 창을 호스트 하는 모든 UI 구성 요소를 지원 해야 합니다는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스입니다. 기본 핵심 편집기 텍스트 보기 포함 주식 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 현재 IntelliSense 기능을 유지 하려면 구현 합니다. 대부분의 경우 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 나타내는 항목의 하위 집합에서 구현 된 인터페이스는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> 인터페이스입니다. IntelliSense UI 처리, 캐럿 및 선택 조작 및 단순 텍스트 대체 기능 하위 집합에 포함 되어 있습니다. 또한는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스 있도록 별도 IntelliSense "subject" 및 "컨텍스트" 컨텍스트에 대해 사용 되는 텍스트 버퍼에 직접 존재 하지 않는 주제에 대 한 IntelliSense를 제공할 수 있습니다.  
  
#### <a name="ivsintellisensehostgethostflags"></a>IVsIntellisenseHost.GetHostFlags  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 공급자 인터페이스를 구현 해야 합니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost.GetHostFlags%2A> 메서드 클라이언트 IntelliSense 어떤 유형의 호스트 기능을 결정할 수 있도록 지원 합니다.  
  
 에 정의 된 호스트 플래그 [IntelliSenseHostFlags](../extensibility/intellisensehostflags.md), 아래에 요약 되어 있습니다.  
  
|IntelliSense 호스트 플래그|설명|  
|----------------------------|-----------------|  
|IHF_READONLYCONTEXT|설정 플래그 즉 상황에 맞는 버퍼가 읽기 전용 및 편집 내 에서만 발생 제목 텍스트입니다.|  
|IHF_NOSEPERATESUBJECT|즉, 플래그는 있는 설정은 별도 IntelliSense 제목 없음입니다. 주체 있는 상황에 맞는 버퍼와 같은 기존에서는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView> IntelliSense 시스템입니다.|  
|IHF_SINGLELINESUBJECT|주체 하지 않은 플래그 즉 설정에서 단일 줄 편집와 같은 지원 되는 여러 줄을 **조사식** 창입니다.|  
|IHF_FORCECOMMITTOCONTEXT|이 플래그가 설정 된 상황에 맞는 버퍼를 업데이트 해야 하는 경우 무시 되는 상황에 맞는 버퍼에서 읽기 전용 플래그 및 편집 하려면 호스트 수 있습니다.|  
|IHF_OVERTYPE|겹쳐쓰기 모드에서 주체 또는 상황에 맞는) (에서 편집 해야 합니다.|  
  
#### <a name="ivsintellisensehostbeforecompletorcommit-and-ivsintellisensehostaftercompletorcommit"></a>IVsIntellisenseHost.BeforeCompletorCommit 및 IVsIntellisenseHost.AfterCompletorCommit  
 이러한 콜백 메서드 전에 및 텍스트 전처리 및 후 처리를 사용 하도록 설정 하려면 커밋된 후 완료 창에서 호출 됩니다.  
  
#### <a name="ivsintellisensecompletor"></a>IVsIntellisenseCompletor  
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseCompletor> 인터페이스는 통합된 개발 환경 (IDE)에서 사용 되는 표준 완료 창의 공동 creatable 버전입니다. 모든 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsIntellisenseHost> 인터페이스가 completor 인터페이스를 사용 하 여 IntelliSense를 신속 하 게 구현할 수 있습니다.  
  
## <a name="see-also"></a>참고자료  
 <xref:Microsoft.VisualStudio.TextManager.Interop>
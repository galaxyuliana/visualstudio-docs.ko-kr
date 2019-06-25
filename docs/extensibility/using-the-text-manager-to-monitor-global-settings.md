---
title: 전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - monitor global settings
- editors [Visual Studio SDK], legacy - text manager
ms.assetid: 023e7671-cf65-419c-9bc1-3c4ee92aa436
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 494e61c7239eb2caacd3facdddbe2cd26b3d0a73
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66336988"
---
# <a name="use-the-text-manager-to-monitor-global-settings"></a>전역 설정을 모니터링 하는 텍스트 관리자를 사용 하 여
핵심 편집기를 구현 하는 경우 이러한 변경 내용은 편집기 인스턴스에 영향을 줄 수 있으므로 전역 설정에 대 한 변경 내용을 모니터링 해야 합니다. 텍스트 관리자에 의해 발생 하는 이벤트를 수신 하 여 변경 내용을 추적할 수 있습니다. 예를 들어, 코어 편집기에서 해당 문서 데이터 개체와 같은 모양이 나 구성 요소의 동작에 대 한 전역 기본 설정을 지정 하는 경우 텍스트 관리자는이 정보를 저장 및 영향을 받는 모든 클라이언트에 통신 합니다.

## <a name="text-manager-functions"></a>텍스트 manager 함수
 텍스트 관리자는 다음과 같은 설정의 수에 대 한 이벤트를 발생 시킵니다.

- 소스 코드 제어에서 버퍼 인지 여부

- 파일 변경 알림을 등록 하는 방법

- 특정 버퍼를 사용 하 여 연결 된 뷰를 추적 하는 방법

- 텍스트 색 지정 기본 설정

- 기본 공간 및 탭

  지정된 된 언어에 고유한 기본 텍스트 관리자가 관리 되지 않습니다. 이러한 설정은 각 언어 서비스에 의해 관리 되어야 합니다.

  제공 하는 텍스트 관리자에 대 한 이벤트 알림을 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManagerEvents> 인터페이스입니다. 이 인터페이스를 구현 합니다. 클라이언트에서 이벤트를 처리 하는 개체는 텍스트 관리자 발생 합니다. 사용 하 여 이러한 이벤트에 대 한 등록을 <xref:Microsoft.VisualStudio.OLE.Interop.IConnectionPointContainer> 텍스트 관리자 인터페이스입니다.

## <a name="see-also"></a>참고자료
- [핵심 편집기 내에서](../extensibility/inside-the-core-editor.md)
- [편집기 기능](https://msdn.microsoft.com/library/bdac940d-1f14-4019-a01f-fd0bb3dc7198)
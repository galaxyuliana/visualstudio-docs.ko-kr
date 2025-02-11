---
title: VSTextView 개체 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSTextView
helpviewer_keywords:
- VSTextView object, reference
- views [Visual Studio SDK], reference
ms.assetid: 78272ddc-9718-4c65-a94e-a44a2e8d54f4
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a5d3983dcefd515a43d573166c9bd772fd23bf0a
ms.sourcegitcommit: 5216c15e9f24d1d5db9ebe204ee0e7ad08705347
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68924148"
---
# <a name="vstextview-object"></a>VSTextView 개체
텍스트 뷰는 사용자가 텍스트 버퍼의 유니코드 텍스트를 보고 편집할 수 있도록 하는 창입니다. 기본적으로 뷰는 대부분의 사용자가 편집기로 참조 하는 것입니다. 뷰는 다양 한 텍스트 계층 (자동 줄 바꿈, 개요 텍스트 등)에 의해 버퍼에서 분리 되기 때문에 버퍼의 텍스트를 정확 하 게 표현 하는 것이 보장 되지 않습니다. 텍스트 보기에 대 한 자세한 내용은 [레거시 API를 사용 하 여 theText View에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)를 참조 하세요.

 다음 표에서는 <xref:Microsoft.VisualStudio.TextManager.Interop.VsTextView> 개체의 인터페이스를 보여 줍니다.

|인터페이스|Description|
|---------------|-----------------|
|[IDropSource](/windows/desktop/api/oleidl/nn-oleidl-idropsource)|표준 OLE 인터페이스입니다.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IDropTarget>|표준 OLE 인터페이스입니다.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IObjectWithSite>|표준 OLE 인터페이스입니다.|
|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|표준 OLE 인터페이스입니다.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCompoundAction>|복합 작업 (즉, 단일 실행 취소/다시 실행 단위로 그룹화 된 작업)을 만들 수 있도록 합니다.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>|뷰를 관리 하 고 액세스 하는 기본 메서드를 제공 합니다. `IVsTextView`는 스레드로부터 안전 하지 않습니다.|
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowPane>|창 창을 만들고 관리 합니다.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLayeredTextView>|텍스트 레이어와 상호 작용 합니다.|
|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsThreadSafeTextView>|다른 스레드에서 뷰에서 작업을 수행 합니다.|

## <a name="see-also"></a>참고자료
- [그림 편집](https://www.microsoft.com/download/details.aspx?id=55984)
- [VSTextBuffer 개체](../extensibility/vstextbuffer-object.md)
- [레거시 API를 사용 하 여 theText view에 액세스](../extensibility/accessing-thetext-view-by-using-the-legacy-api.md)
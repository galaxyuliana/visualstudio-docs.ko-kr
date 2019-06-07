---
title: 실행 취소 하 고 레거시 API를 사용 하 여 다시 실행 관리 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK], legacy - undo management
ms.assetid: 838c0ddf-fdf3-4df1-8d21-79610b8ba0b1
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8a93b4fd12cd9a0bd2e5a5f3c70486e370545a9
ms.sourcegitcommit: 12f2851c8c9bd36a6ab00bf90a020c620b364076
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/06/2019
ms.locfileid: "66747641"
---
# <a name="manage-undo-and-redo-by-using-the-legacy-api"></a>실행 취소를 관리 하 고 기존 API를 사용 하 여 다시 실행
편집기는 코드를 수정 하는 경우 최근 변경 내용이 되돌릴 수 있도록 하는 실행 취소 작업을 지원 해야 합니다. 구현 하는 대부분의 편집기 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] .NET Framework 통합된 개발 환경 (IDE)에서 자동으로 제공 하는 실행 취소 지원 있고 사용할 수 있습니다.

## <a name="in-this-section"></a>단원 내용
- [방법: 실행 취소 관리 구현](../extensibility/how-to-implement-undo-management.md) 단일 또는 여러 뷰가 포함 된 편집기에 대 한 실행 취소 기능을 제공 합니다.

- [방법: 실행 취소 스택을 지웁니다.](../extensibility/how-to-clear-the-undo-stack.md) 실행 취소 스택에 선택을 취소 하는 방법에 설명 합니다.

- [방법: 연결 된 실행 취소 관리를 사용 하 여](../extensibility/how-to-use-linked-undo-management.md) Incorporates 실행 취소 관리 하는 편집기에 연결 합니다.

## <a name="reference"></a>참조
 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsChangeTrackingUndoManager> 여러 뷰를 지 원하는 편집기에 대 한 실행 취소 관리를 제공 합니다.

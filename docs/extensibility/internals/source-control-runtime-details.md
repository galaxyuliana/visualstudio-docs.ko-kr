---
title: 소스 제어 런타임 세부 정보 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e84fd82c5da5deea2d718baf67799e5bf877131
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66322557"
---
# <a name="source-control-runtime-details"></a>소스 제어 런타임 세부 정보
사용자는 마법사와 같은 자동화 컨트롤러를 통해 또는 소스 제어에 프로젝트의 파일을 추가 하는 경우 프로젝트를 소스 제어에 추가 됩니다. 프로젝트에서는 자체에 대 한 소스 제어; 것 해당 소스 제어를 지원 하지만 수동으로를 추가 해야 합니다.

## <a name="registering-with-a-source-control-package"></a>소스 제어 패키지를 사용 하 여 등록
 환경을 호출 하는 프로젝트에서 파일을 소스 제어에 추가할 때 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> 를 소스 제어 시스템에서 쿠키로 사용 되는 4 개의 불투명 문자열을 제공 합니다. 프로젝트 파일에서 이러한 문자열을 저장 합니다. 이러한 문자열에 전달 되어야 (Visual Studio 구성 요소 소스 제어 패키지를 관리 하는) 소스 제어 스텁 프로젝트 형식의 시작 시 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>입니다. 이 적절 한 원본 제어 패키지를 로드 하 고 전달의 구현에 대 한 호출 `IVsSccManager2::RegisterSccProject`합니다.

## <a name="see-also"></a>참고 항목
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>
- [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)
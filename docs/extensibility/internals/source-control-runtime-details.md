---
title: 소스 제어 런타임 세부 정보 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- source control [Visual Studio SDK], runtime details
ms.assetid: 1acd30e0-f98c-4bde-b9cd-4076845887df
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 3f7501a25596fc0a818277d164337bb0d4e4e077
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56618798"
---
# <a name="source-control-runtime-details"></a>소스 제어 런타임 세부 정보
사용자는 마법사와 같은 자동화 컨트롤러를 통해 또는 소스 제어에 프로젝트의 파일을 추가 하는 경우 프로젝트를 소스 제어에 추가 됩니다. 프로젝트에서는 자체에 대 한 소스 제어; 것 해당 소스 제어를 지원 하지만 수동으로를 추가 해야 합니다.

## <a name="registering-with-a-source-control-package"></a>소스 제어 패키지를 사용 하 여 등록
 환경을 호출 하는 프로젝트에서 파일을 소스 제어에 추가할 때 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A> 를 소스 제어 시스템에서 쿠키로 사용 되는 4 개의 불투명 문자열을 제공 합니다. 프로젝트 파일에서 이러한 문자열을 저장 합니다. 이러한 문자열에 전달 되어야 (Visual Studio 구성 요소 소스 제어 패키지를 관리 하는) 소스 제어 스텁 프로젝트 형식의 시작 시 호출 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>입니다. 이 적절 한 원본 제어 패키지를 로드 하 고 전달의 구현에 대 한 호출 `IVsSccManager2::RegisterSccProject`합니다.

## <a name="see-also"></a>참고 항목
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2.RegisterSccProject%2A>
- <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2.SetSccLocation%2A>
- [소스 제어 지원](../../extensibility/internals/supporting-source-control.md)
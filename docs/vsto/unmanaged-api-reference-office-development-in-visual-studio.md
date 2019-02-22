---
title: 관리 되지 않는 API 참조 (Visual Studio에서 Office 개발)
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- Office development in Visual Studio, reference
- Office development in Visual Studio, unmanaged API reference
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 238ed42d48903d2d0ef26384245cff80785a8ebb
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56643706"
---
# <a name="unmanaged-api-reference-office-development-in-visual-studio"></a>관리 되지 않는 API 참조 (Visual Studio에서 Office 개발)

2007 Microsoft Office 시스템부터 Office 응용 프로그램 사용 합니다 [IManagedAddin 인터페이스](../vsto/imanagedaddin-interface.md) 에서 VSTO 추가 기능 로더 구성 요소에 포함 된 호출에 대 한 인터페이스를 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]입니다. 이 구성 요소는 부하로 관리 되는 vsto 추가 하는 데 사용 됩니다. 이 인터페이스를 구현하여 사용자 고유의 VSTO 추가 기능 로더 구성 요소를 만들 수 있습니다.

> [!NOTE]
> Office 환경을 확장 하는 솔루션을 개발 하는 데 관심이 [여러 플랫폼](https://dev.office.com/add-in-availability)? 새 확인해 [Office 추가 기능 모델](https://dev.office.com/docs/add-ins/overview/office-add-ins)합니다. Office 추가 기능의 VSTO 추가 기능 및 솔루션에 비해 작은 사용 공간이 있고 거의 모든 웹 프로그래밍 기술을, HTML5, JavaScript, CSS3, XML 등을 사용 하 여 빌드할 수 있습니다.

## <a name="in-this-section"></a>단원 내용

[IManagedAddin 인터페이스](../vsto/imanagedaddin-interface.md)

Office 애플리케이션에서 관리되는 VSTO 추가 기능을 로드 및 언로드하기 위해 구현할 수 있는 COM 인터페이스입니다.

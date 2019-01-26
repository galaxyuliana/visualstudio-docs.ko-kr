---
title: '방법: 관리 코드 오류에 대한 작업 항목 만들기'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.topic: conceptual
helpviewer_keywords:
- managed code, creating work items for code defects
- code analysis, creating work items
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 1cb63612194148b5f3ea1f90d7c57e59fb84edbc
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54941829"
---
# <a name="how-to-create-a-work-item-for-a-managed-code-defect"></a>방법: 관리 코드 오류에 대한 작업 항목 만들기

Visual Studio 내에서 작업 로그 항목을 작업 항목 추적 기능을 사용할 수 있습니다. 이 기능을 사용 하려면 프로젝트의 일부 여야 Azure DevOps 프로젝트를 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)]입니다.

## <a name="to-create-a-work-item-for-managed-code-defect"></a>관리 코드 오류에 대 한 작업 항목을 만들려면

1. 에 **코드 분석** 창에서 경고를 선택 합니다.

2. 선택 **동작**, 선택한 **작업 항목 만들기** 만들려는 작업 항목의 유형을 선택 합니다.

     오류 정보를 지정할 수 있습니다 새 작업 항목이 생성 됩니다.

## <a name="to-create-a-work-item-for-multiple-managed-code-defects"></a>여러 관리 코드 오류에 대 한 작업 항목을 만들려면

1. 에 **오류 목록**, 여러 경고를 선택 하 고 경고를 마우스 오른쪽 단추로 클릭 합니다.

2. 가리킨 **작업 항목 만들기** 만들려는 작업 항목의 유형을 클릭 합니다.

     버그 정보를 지정할 수 있도록 선택한 모든 경고에 대 한 단일 작업 항목 생성 됩니다.
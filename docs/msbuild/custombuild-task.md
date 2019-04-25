---
title: CustomBuild 작업 | Microsoft Docs
ms.date: 03/10/2019
ms.topic: reference
f1_keywords:
- vc.task.custombuild
dev_langs:
- VB
- CSharp
- C++
- jsharp
- C++
helpviewer_keywords:
- MSBuild (Visual C++), CustomBuild task
- CustomBuild task (MSBuild (Visual C++))
author: mikeblome
ms.author: mblome
ms.workload:
- multiple
ms.openlocfilehash: 197128fadb660ab06686d13ec304a5d9d1698070
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62778139"
---
# <a name="custombuild-task"></a>CustomBuild 작업

Visual C++ 컴파일러 도구인 cmd.exe를 래핑합니다.

## <a name="parameters"></a>매개 변수

다음 표에서는 **CustomBuild** 작업의 매개 변수에 대해 설명합니다.

|매개 변수|설명|
|---------------|-----------------|
|**BuildSuffix**|선택적 **string** 매개 변수입니다.|
|**Sources**|필수 **ITaskItem[]** 매개 변수입니다.|
|**TrackerLogDirectory**|선택적 **string** 매개 변수입니다.|

## <a name="see-also"></a>참고 항목

[작업 참조](../msbuild/msbuild-task-reference.md)
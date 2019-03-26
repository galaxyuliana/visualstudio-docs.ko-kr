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
ms.author: Michael.Blome
ms.workload:
- multiple
ms.openlocfilehash: 183cdefbca29db486b84cb61f90501507e298838
ms.sourcegitcommit: 4ffb7be5384ad566ce46538032bf8561754c61a4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2019
ms.locfileid: "58070473"
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
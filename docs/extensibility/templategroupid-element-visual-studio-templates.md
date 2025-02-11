---
title: TemplateGroupID 요소 (Visual Studio 템플릿) | Microsoft Docs
ms.date: 11/04/2016
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- http://schemas.microsoft.com/developer/vstemplate/2005#TemplateGroupID
helpviewer_keywords:
- TemplateGroupID element [Visual Studio Templates]
- <TemplateGroupID> element [Visual Studio Templates]
ms.assetid: bce7b49a-90bc-4691-aff3-a87e209f6d83
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 4b4e0ccae38b79cf8efb4b7b426fb65ae909c5d5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66316598"
---
# <a name="templategroupid-element-visual-studio-templates"></a>TemplateGroupID 요소(Visual Studio 템플릿)
항목 템플릿이 표시되는 프로젝트 종류를 지정합니다. 이 요소는 상당한 [ShowByDefault (Visual Studio 템플릿)](../extensibility/showbydefault-visual-studio-templates.md) 로 설정 된 `false`합니다. 때 [ShowByDefault (Visual Studio 템플릿)](../extensibility/showbydefault-visual-studio-templates.md) 로 설정 된 `true`, 항목 템플릿에 모든 프로젝트 형식에서 사용할 수 있습니다.

 \<VSTemplate> \<TemplateData> \<TemplateGroupID>

## <a name="syntax"></a>구문

```
<TemplateGroupID> ... </TemplateGroupID>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성
 없음

### <a name="child-elements"></a>자식 요소
 없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[TemplateData](../extensibility/templatedata-element-visual-studio-templates.md)|템플릿을 분류하고 **새 프로젝트** 또는 **새 항목 추가** 대화 상자에서 템플릿이 표시되는 방식을 정의합니다.|

## <a name="text-value"></a>텍스트 값
 텍스트 값은 필수입니다.

 텍스트는 항목 템플릿 범주에 대한 식별자를 지정합니다.

## <a name="remarks"></a>설명
 `TemplateGroupID`는 요소입니다.

 값을 `TemplateGroupID` 프로젝트 시스템 등록 함께 사용 하는 요소 (HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio\\ *\<버전 번호 >* \Projects\\) 에 표시 되는 템플릿을 필터링 하는 **새 항목 추가** 대화 상자.

|Visual C++ 값|의미|
|------------------------|-------------|
|VC-Native|네이티브 프로젝트에 사용됩니다. 프로젝트 형식을 확인할 수 없는 경우에는 기본값입니다.|
|VC-Managed|관리되는(/clr) 프로젝트에 사용됩니다.|
|VC-Windows|Windows 플랫폼(네이티브/관리/저장소)을 대상으로 하는 모든 프로젝트에 사용됩니다.|
|WinRT-Native-UAP|Windows 10 스토어 프로젝트에 사용됩니다.|
|CodeSharing-Native|공유 항목 프로젝트에 사용됩니다.|
|WinRT-Native-6.3|Windows 8.1 스토어 프로젝트에 사용됩니다.|
|WinRT-Native-Phone-6.3|Windows Phone 8.1 프로젝트에 사용됩니다.|
|WinRT-Native|Windows 8.0 스토어 프로젝트에 사용됩니다.|
|VC-Android|Android 프로젝트에 사용됩니다.|

## <a name="see-also"></a>참고 항목
- [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)
- [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)
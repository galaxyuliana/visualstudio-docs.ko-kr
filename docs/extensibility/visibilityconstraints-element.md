---
title: VisibilityConstraints 요소 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VisibilityConstraints
helpviewer_keywords:
- VSCT XML schema elements, VisibilityConstraints
- VisibilityConstraints element (VSCT XML schema)
ms.assetid: d6dcd314-6fe4-4693-a189-91fa026c7b34
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: b5dfbeb3c45e05c93554aae9b17a42c265408bc3
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62839038"
---
# <a name="visibilityconstraints-element"></a>VisibilityConstraints 요소
VisibilityConstraints 요소는 정적 도구 모음 및 명령 그룹의 표시 여부를 결정합니다. 표시 여부는 처음에 의해 제어 됩니다는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage를 로드 하지 않고 통합된 개발 환경 (IDE)입니다.

## <a name="syntax"></a>구문

```xml
<VisibilityConstraints>
  <VisibilityItem />
  <VisibilityItem />
</VisibilityConstraints>
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|

### <a name="child-elements"></a>자식 요소

|요소|설명|
|-------------|-----------------|
|[VisibilityItem 요소](../extensibility/visibilityitem-element.md)|도구 모음 및 명령 정적 표시 여부를 결정 합니다.|
|[VisibilityConstraints](../extensibility/visibilityconstraints-element.md)|정적 도구 모음 및 명령 그룹의 표시 여부를 결정합니다.|

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[CommandTable 요소](../extensibility/commandtable-element.md)|VSPackage는 IDE를 제공 하는 명령 (예: 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자)를 나타내는 모든 요소를 정의 합니다.|

## <a name="example"></a>예제

```xml
<VisibilityConstraints>
  <VisibilityItem guid="cmdSetGuidMyProductCommands"     id="cmdidAddWidget"
    context="guidNotViewSourceMode"/>
</VisibilityConstraints>
```

## <a name="see-also"></a>참고자료
- [VisibilityItem 요소](../extensibility/visibilityitem-element.md)
- [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)

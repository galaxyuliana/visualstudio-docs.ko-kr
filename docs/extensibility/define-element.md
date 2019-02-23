---
title: 요소를 정의 합니다. | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT XML schema elements, Define
- Define element (VSCT XML schema)
ms.assetid: 5aee74e3-de41-4dc6-9618-93e158af56dd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: ccb14705b4d799e1f7fa6de4728ee8f7fc7b3fb4
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56706641"
---
# <a name="define-element"></a>요소를 정의 합니다.
기호 이름 및 값 쌍을 정의합니다. 조건부 특성에서이 기호를 평가할 수 있습니다. 자세한 내용은 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다. 참고 항목의 [Symbols 요소](../extensibility/symbols-element.md)합니다.

## <a name="syntax"></a>구문

```
<Define name="Mode" value="Standard" />
```

## <a name="attributes-and-elements"></a>특성 및 요소
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.

### <a name="attributes"></a>특성

|특성|설명|
|---------------|-----------------|
|name|필수 요소. 기호 이름:<br /><br /> name="Mode"|
|value|필수 요소. 기호의 값:<br /><br /> 값 = "Standard"|
|조건|선택 사항입니다. 자세한 내용은 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|

### <a name="child-elements"></a>자식 요소
 없음

### <a name="parent-elements"></a>부모 요소

|요소|설명|
|-------------|-----------------|
|[CommandTable 요소](../extensibility/commandtable-element.md)|통합된 개발 환경 (IDE)에 VSPackage가 제공 하는 명령을 나타내는 모든 요소를 정의 합니다. 예를 들어 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자입니다.|

## <a name="example"></a>예제

```
<Define name="DEMO_UI"/>
<Define name="MODE" value="Standard"/>
```

## <a name="see-also"></a>참고자료
- [Visual Studio 명령 테이블 (.vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
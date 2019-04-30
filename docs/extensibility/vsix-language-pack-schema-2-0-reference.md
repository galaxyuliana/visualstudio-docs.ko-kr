---
title: VSIX 언어 팩 스키마 2.0 참조 | Microsoft Docs
ms.date: 10/26/2017
ms.topic: conceptual
helpviewer_keywords:
- language pack
- localize vsix
- localize package
- localize extension
ms.assetid: 2a2932bc-cdbe-4d32-91fa-a3e0474f9098
ms.author: dagriffe
author: dgriffen
manager: jillfra
ms.workload:
- dagriffe
ms.openlocfilehash: acea36031b98693e1d618986720d9932f76a0a63
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62953103"
---
# <a name="vsix-language-pack-schema-20-reference"></a>VSIX 언어 팩 스키마 2.0 참조

VSIX 언어 팩 스키마 VSIX 패키지에 대 한 지역화 된 설치 정보를 제공 합니다. 이 스키마의 버전 2.0에서 추가로 지역화 요소를 지원 합니다.

## <a name="language-pack-schema"></a>언어 팩 스키마

언어 팩 파일의 루트 요소는 `<PackageLanguagePackManifest>`의 특성을 사용 하 여 `Version`, 언어 팩 형식의 버전입니다. 설정 하 여 매니페스트에 지정 된 언어 팩 형식의 버전 2.0에 설명 합니다 `Version` 특성 값을 `Version="2.0.0"`입니다. 루트 요소에는 정확히 하나의 자식 포함 `<Metadata>` 요소입니다.

### <a name="packagelanguagepackmanifest-element"></a>PackageLanguagePackManifest 요소

내는 `<PackageLanguagePackManifest>` 요소는 다음과 같은 요소가 있어야 합니다.

|제목|설명|
|-----------|-----------------|
|`<Metadata>`| 모든 지역화 된 패키지 메타 데이터를 포함 하는 요소

### <a name="metadata-element"></a>메타 데이터 요소

내는 `<Metadata>` 요소는 다음과 같은 요소가 있습니다.

|제목|설명|
|-----------|-----------------|
|`<DisplayName>`|확장을 설치의 지역화 된 이름|
|`<Description>`|확장을 설치의 지역화 된 설명|
|`<License>`| 확장의 라이선스의 지역화 된 버전에 대 한 경로|
|`<MoreInfo>`| 확장에 대 한 지역화 된 정보에 대 한 링크|
|`<ReleaseNotes>`| 경로 또는 지역화 된 버전의 릴리스 정보에 대 한 링크|
|`<Icon>`| 확장 아이콘의 지역화 된 버전에 대 한 경로|

### <a name="sample-manifest"></a>샘플 매니페스트

```xml
<?xml version="1.0" encoding="utf-8"?>
<PackageLanguagePackManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011">
  <Metadata>
    <DisplayName>Arbol de Familia</LocalizedName>
    <Description> Esta extensión pone control personalizado en la caja de herramientas por manejar información de familia.</Description>
    <MoreInfo> http://www.contoso.com/products/es/ArbolDeFamilia.htm</MoreInfo>
    <License>Eula.rtf</License>
    <ReleaseNotes>ReleaseNotes.rtf</ReleaseNotes>
    <Icon>Icon.png</Icon>
  </Metadata>
</PackageLanguagePackManifest>
```

## <a name="see-also"></a>참고자료

|제목|설명|
|-----------|-----------------|
|[VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)|VSIX 패키지 지역화 된 설치 지원을 제공 하는 방법을 보여 줍니다.|
|[VSIX 확장 스키마 2.0 참조](../extensibility/vsix-extension-schema-2-0-reference.md)|VSIX 매니페스트에의 콘텐츠를 설명 하는 *.vsix* 배포 파일입니다. 배포 파일을 사용 하면 Visual Studio 확장을 사용 하 여 설치 합니다 **확장 및 업데이트** 대화 상자.|
|[Visual Studio 확장 찾기 및 사용](../ide/finding-and-using-visual-studio-extensions.md)|사용 하는 방법을 보여 줍니다 합니다 **확장 및 업데이트** 설치, 제거, 활성화 및 비활성화 확장 대화 상자.|
---
title: 'CA1824: NeutralResourcesLanguageAttribute로 어셈블리를 표시하세요.'
ms.date: 03/29/2018
ms.topic: reference
f1_keywords:
- CA1824
- MarkAssembliesWithNeutralResourcesLanguage
helpviewer_keywords:
- MarkAssembliesWithNeutralResourcesLanguage
- CA1824
ms.assetid: 10e97f8a-aa6e-47aa-b253-1e5d3a295d82
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 40cb2a3674884a9fb4f1449c9afa2e0a2d27050f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62808562"
---
# <a name="ca1824-mark-assemblies-with-neutralresourceslanguageattribute"></a>CA1824: NeutralResourcesLanguageAttribute로 어셈블리를 표시하세요.

|||
|-|-|
|TypeName|MarkAssembliesWithNeutralResourcesLanguage|
|CheckId|CA1824|
|범주|Microsoft.Performance|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

포함 된 어셈블리를 **ResX**-리소스를 따르지만 없는 <xref:System.Resources.NeutralResourcesLanguageAttribute?displayProperty=fullName> 적용 합니다.

## <a name="rule-description"></a>규칙 설명

<xref:System.Resources.NeutralResourcesLanguageAttribute> 특성에는 앱의 기본 문화권의 리소스 관리자에 게 알립니다. 기본 문화권의 리소스는 앱의 주 어셈블리에 포함 된 경우 및 <xref:System.Resources.ResourceManager> 기본 문화권과 동일한 문화권에 속하는 리소스를 검색에 <xref:System.Resources.ResourceManager> 주 어셈블리에 있는 리소스를 자동으로 사용 대신 위성 어셈블리를 검색 합니다. 이 일반적인 어셈블리 프로브 무시, 첫 번째 리소스를 로드 하 고 작업 집합을 줄일 수에 대 한 조회 성능이 향상 됩니다.

> [!TIP]
> 참조 [리소스 패키징 및 배포](/dotnet/framework/resources/packaging-and-deploying-resources-in-desktop-apps) 프로세스는 <xref:System.Resources.ResourceManager> 리소스 파일에 대 한 프로브를 사용 하 여 합니다.

## <a name="fix-violations"></a>위반 문제를 해결합니다

이 규칙 위반 문제를 해결 하려면 어셈블리에 특성을 추가 하 고 언어 중립 문화권의 리소스를 지정 합니다.

### <a name="to-specify-the-neutral-language-for-resources"></a>중립 언어 리소스를 지정 하려면

1. **솔루션 탐색기**프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택한 **속성**합니다.

2. 선택 된 **응용 프로그램** 탭을 선택한 후 **어셈블리 정보**합니다.

   > [!NOTE]
   > 프로젝트는.NET Standard 또는.NET Core 프로젝트를 선택 합니다 **패키지** 탭 합니다.

3. 언어를 선택 합니다 **중립 언어** 또는 **어셈블리의 중립 언어** 드롭 다운 목록.

4. **확인**을 선택합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시 하는 경우

이 규칙에서 경고를 표시 하지 않을 것입니다. 그러나 시작 성능이 저하 될 수 있습니다.

## <a name="see-also"></a>참고자료

- <xref:System.Resources.NeutralResourcesLanguageAttribute>
- [데스크톱 앱 (.NET)의 리소스](/dotnet/framework/resources/)
- [-리소스 문자열은 ca1703](../code-quality/ca1703-resource-strings-should-be-spelled-correctly.md)
- [CA1701-리소스 문자열 복합 단어에는 올바르게 표기를 사용 해야](../code-quality/ca1701-resource-string-compound-words-should-be-cased-correctly.md)
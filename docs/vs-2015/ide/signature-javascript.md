---
title: '&lt;서명&gt; (JavaScript) | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- <signature> JavaScript XML tag
- signature JavaScript XML tag
ms.assetid: 319138e7-cfbe-4b37-9643-2ddb7f9c63d4
caps.latest.revision: 16
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 02a4c36f3969ca0f9ef61e817afb82eb8247f041
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54780319"
---
# <a name="ltsignaturegt-javascript"></a>&lt;서명&gt; (JavaScript)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

함수 또는 오버 로드 된 함수에 대 한 설명서를 제공 하는 방법에 대 한 관련된 요소 집합을 그룹화 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<signature externalid="id" externalFile="filename"  
    helpKeyword="keyword" locid="descriptionID">  
</signature>   
```  
  
#### <a name="parameters"></a>매개 변수  
 `externalid`  
 선택 사항입니다. 경우는 `format` 특성에 대 한는 [ \<loc >](../ide/loc-javascript.md) 요소는 `vsdoc`,이 특성 ID 서명과 사용 하 여 연결 된 XML 코드를 찾는 데 사용 하는 멤버를 지정 합니다. 달리는 `locid` 특성이이 특성에이 ID는 멤버의 모든 요소를 로드 하도록 지정 합니다. 모든 관련된 설명 정보를 XML 코드에 있는 시그니처에서 지정 된 요소를 사용 하 여도 병합 됩니다. 와 같은 추가 요소를 지정할 수 있습니다이 `<capability>`, 소스 파일에서이 지정 하지 않고 사이드카 파일에 있습니다. `externalid` 선택적 특성이입니다.  
  
 `externalFile`  
 선택 사항입니다. 검색할 파일의 이름을 지정 합니다 `externalid`합니다. 없으면이 특성은 무시 `externalid` 표시 됩니다. 선택적 특성입니다. 기본값은 파일 확장명이.xml.js 대신 했지만 현재 파일의 이름입니다. 기본적으로 지역화를 위한 관리 되는 리소스 조회 규칙 파일을 찾으려고 사용 됩니다.  
  
 `helpKeyword`  
 선택 사항입니다. 에 대 한 F1 도움말 키워드입니다.  
  
 `locid`  
 선택 사항입니다. 필드에 대 한 지역화 정보에 대 한 식별자입니다. 식별자는 멤버에 해당 하는 ID 또는를 `name` 특성 OpenAjax 메타 데이터에 의해 정의 된 메시지 묶음의 값입니다. 식별자 형식에 지정 된 형식에 따라 달라 집니다 합니다 [ \<loc >](../ide/loc-javascript.md) 태그입니다.  
  
## <a name="remarks"></a>주의  
 하나를 사용 하 여 `<signature>` 각각에 대 한 요소에서.js 파일을 하나 사용 하 여 함수 설명 오버 로드 된 `<signature>` 지정 된 각 외부 멤버 ID에 대 한 요소입니다.  
  
 `<signature>` 문 앞에서 함수 본문의 요소를 배치 해야 합니다. 사용 하는 경우 [ \<요약 >](../ide/summary-javascript.md), [ \<param >](../ide/param-javascript.md), 또는 [ \<반환 >](../ide/returns-javascript.md) 사용 하 여 요소를 `<signature>` 요소 내 다른 요소를 배치 합니다 `<signature>` 블록입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제를 사용 하는 방법을 보여 줍니다는 `<signature>` 요소입니다.  
  
```javascript  
// Use of <signature> with externalid.  
// Requires use of the <loc> tag to identify the external functions.  
function illuminate(light) {  
    /// <signature externalid='M:Windows.Devices.Light.Illuminate()' />  
    /// <signature externalid='M:Windows.Devices.Light.Illuminate(System.Int32)'>  
    ///   <param name='light' type='Number' />  
    /// </signature>  
}  
  
// Use of <signature> for overloads implemented in JavaScript.  
function add(a, b) {  
    /// <signature>  
    /// <summary>function summary 1</summary>  
    /// <param name="a" type="Number">The first number</param>  
    /// <param name="b" type="Number">The second number</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 2 – differ by number of params</summary>  
    /// <param name="a" type="Number">Only 1 parameter</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 3 – differ by parameter type</summary>  
    /// <param name="a" type="Number">Number parameter</param>  
    /// <param name="b" type="String">String parameter</param>  
    /// <returns type="Number" />  
    /// </signature>  
    /// <signature>  
    /// <summary>function summary 4 – differ by return type</summary>  
    /// <param name="a" type="Number">The first number</param>  
    /// <param name="b" type="Number">The second number</param>  
    /// <returns type="String" />  
    /// </signature>  
  
    return a + b;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [XML 문서 주석](../ide/xml-documentation-comments-javascript.md)

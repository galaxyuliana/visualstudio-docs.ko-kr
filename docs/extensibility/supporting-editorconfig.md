---
title: EditorConfig 지원 하도록 언어 서비스 확장
ms.date: 11/22/2017
ms.topic: conceptual
helpviewer_keywords:
- editorconfig [extensibility]
- editorconfig, supporting in a language service
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 5c6974c7943a751f50cafb0b141ba9c1dfc85677
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353501"
---
# <a name="supporting-editorconfig-for-your-language-service"></a>EditorConfig 언어 서비스에 대 한 지원

[EditorConfig](http://editorconfig.org/) 파일을 프로젝트 단위로에서 들여쓰기 크기와 같은 공통 텍스트 편집기 옵션을 설명 하는 데 사용 합니다. EditorConfig 파일에 대 한 Visual Studio의 지원에 대 한 자세한 내용은 참조 하세요 [EditorConfig를 사용 하 여 이식 가능한 편집기 설정 만들기](../ide/create-portable-custom-editor-options.md)합니다.

대부분의 경우 Visual Studio 언어 서비스를 구현할 때 EditorConfig 유니버설 속성을 지원하기 위해 추가 작업이 필요하지 않습니다. 사용자가 파일을 열면 코어 편집기에서 .editorconfig 파일을 자동으로 검색하여 읽은 다음 적절한 텍스트 버퍼와 보기 옵션을 설정합니다. 그러나 탭, 공백 등 편집에 대 한 일부 언어 서비스 전역 설정을 사용 하는 것이 아니라 적절 한 상황별 텍스트 보기 옵션을 사용 하도록 선택할 합니다. 이러한 경우 EditorConfig 파일을 지원하도록 언어 서비스를 업데이트해야 합니다.

다음은 전역 바꿔 EditorConfig 파일을 지원 하도록 언어 서비스를 업데이트 하는 데 필요한 변경 내용을 _언어별_ 옵션을 _상황에 맞는_ 옵션:

## <a name="indent-style"></a>들여쓰기 스타일

언어별 옵션 | 상황에 맞는 옵션
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.fInsertTabs<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs|!textBufferOptions.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)<br/>!textView.Options.GetOptionValue(DefaultOptions.ConvertTabsToSpacesOptionId)

## <a name="indent-size"></a>들여쓰기 크기

언어별 옵션 | 상황에 맞는 옵션
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uIndentSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.IndentSize|textBufferOptions.GetOptionValue(DefaultOptions.IndentSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.IndentSizeOptionId)

## <a name="tab-size"></a>탭 크기

언어별 옵션 | 상황에 맞는 옵션
-------|--------
Microsoft.VisualStudio.TextManager.Interop.LANGPREFERENCES.uTabSize<br/>Microsoft.VisualStudio.Package.LanguagePreferences.InsertTabs.TabSize|textBufferOptions.GetOptionValue(DefaultOptions.TabSizeOptionId)<br/>textView.Options.GetOptionValue(DefaultOptions.TabSizeOptionId)

## <a name="see-also"></a>참고자료

- [EditorConfig를 사용 하 여 이식 가능한 편집기 설정 만들기](../ide/create-portable-custom-editor-options.md)
- [편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)
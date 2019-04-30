---
title: 텍스트 템플릿에서 이스케이프 시퀀스 사용
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- text templates, escape sequences
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 9c88c9c8769051724855d292bfefb56f69cb8dee
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62906925"
---
# <a name="using-escape-sequences-in-text-templates"></a>텍스트 템플릿에서 이스케이프 시퀀스 사용
텍스트 템플릿에서 텍스트 템플릿 태그를 생성 하 고 (C# 코드에만 해당)에서 이스케이프 시퀀스를 사용할 수 있습니다 이스케이프 제어 문자를 인용 합니다.

 출력 파일에 표준 코드 블록에 대 한 열기 및 닫기 태그를 인쇄 하려면 태그를 다음과 같이 이스케이프 합니다.

```
\<# ... \#>
```

 다른 텍스트 템플릿 지시문 및 코드 블록 태그를 사용 하 여 동일 하 게 수행할 수 있습니다.

 텍스트 블록을 텍스트 템플릿 태그를 이스케이프 하는 데 사용 하는 문자열에 포함 된 경우 다음과 같은 이스케이프 시퀀스를 사용할 수 있습니다.

- 텍스트 템플릿 태그를 이스케이프 수가 짝수인 경우 앞 (\\) 템플릿을 문자 파서 되며 이스케이프 문자가의 절반을 포함 텍스트 템플릿 태그 시퀀스를 포함 합니다. 예를 들어, 텍스트 템플릿에서 이스케이프 문자가 4 개 있는 경우 있습니다 됩니다 두 "\\" 생성된 된 파일에는 문자입니다.

- 텍스트 템플릿 태그 홀수 이스케이프 오는 경우 (\\) 문자 템플릿 파서가 포함 됩니다의 절반을 "\\" 태그 자체 문자 (\<# 또는 #>). 텍스트 템플릿 태그에 태그를 간주 되지 않습니다.

- 경우 이스케이프 (\\)에서 제어 문자 또는 (C#에 해당)의 따옴표를 이스케이프 위치 이외의 순서와 관계 없이 다른 곳에 표시 되는 문자의 문자는 직접 출력 합니다.

## <a name="see-also"></a>참고 항목

- [방법: 이스케이프 시퀀스를 사용하여 템플릿에서 템플릿 생성](../modeling/how-to-generate-templates-from-templates-by-using-escape-sequences.md)
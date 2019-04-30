---
title: '방법: _Analysis_assume을 사용하여 추가 코드 정보 지정'
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
author: mikeblome
ms.author: mblome
manager: wpickett
ms.workload:
- multiple
ms.openlocfilehash: 25ce2a97acd248e546fdfab1a1b5c3f22e085f0c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63403114"
---
# <a name="how-to-specify-additional-code-information-by-using-analysisassume"></a>방법: _Analysis_assume을 사용하여 추가 코드 정보 지정
C 용 코드 분석 도구에 대 한 힌트를 제공할 수 있습니다 /C++ 분석을 처리 하 고 경고를 줄이는 데 도움이 되는 코드입니다. 추가 정보를 제공 하려면 다음 함수를 사용 합니다.

 `_Analysis_assume(`  `expr`  `)`

 `expr` -true로 평가 된다고 간주 되는 식입니다.

 코드 분석 도구를 사용 하는 식을 나타내는 조건 함수 나타나고 식 변경, 예를 들어 변수에 할당 될 때까지 true 남아 있는 지점에서 있다고 가정 합니다.

> [!NOTE]
> `_Analysis_assume` 코드 최적화에 영향을 주지 않습니다. 코드 분석 도구를 사용 하는 외부 `_Analysis_assume` no-op으로 정의 됩니다.

## <a name="example"></a>예제
 다음 코드에서는 `_Analysis_assume` 코드 분석 경고를 해결 하려면 [C6388](../code-quality/c6388.md):

```
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

// calls free and sets ch to null
void FreeAndNull(char* ch);

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

void test( )
{
  char *pc = (char*)malloc(5);
  FreeAndNull(pc);
  _Analysis_assume(pc == NULL);
  f(pc);
}
```

## <a name="see-also"></a>참고 항목
 [__assume](/cpp/intrinsics/assume)
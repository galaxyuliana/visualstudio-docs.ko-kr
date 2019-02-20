---
title: NameSearchOptions | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- NameSearchOptions enumeration
ms.assetid: 67dfbede-2678-47df-b664-5c49841d0b9b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8fa637a5f403a4651541d920c6390204ee579994
ms.sourcegitcommit: 752f03977f45169585e407ef719450dbe219b7fc
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/15/2019
ms.locfileid: "56318617"
---
# <a name="namesearchoptions"></a>NameSearchOptions
기호 및 파일 이름에 대 한 검색 옵션을 지정합니다.

## <a name="syntax"></a>구문

```C++
enum NameSearchOptions {
    nsNone,
    nsfCaseSensitive     = 0x1,
    nsfCaseInsensitive   = 0x2,
    nsfFNameExt          = 0x4,
    nsfRegularExpression = 0x8,
    nsfUndecoratedName   = 0x10,

// For backward compatibility:
    nsCaseSensitive           = nsfCaseSensitive,
    nsCaseInsensitive         = nsfCaseInsensitive,
    nsFNameExt                = nsfCaseInsensitive | nsfFNameExt,
    nsRegularExpression       = nsfRegularExpression | nsfCaseSensitive,
    nsCaseInRegularExpression = nsfRegularExpression | nsfCaseInsensitive
};
```

## <a name="elements"></a>요소
`nsNone`  
지정된 옵션이 없습니다.

`nsfCaseSensitive`  
대/소문자 구분 이름 일치를 적용합니다.

`nsfCaseInsensitive`  
대/소문자 이름 일치를 적용합니다.

`nsfFNameExt`  
경로와 이름을 처리 하 고 filename.ext 이름 일치를 적용 합니다.

`nsfRegularExpression`  
와일드 카드로 별표 (*) 및 물음표 (?)를 사용 하 여 대/소문자 구분 이름 일치를 적용 합니다.

`nsfUndecoratedName`  
기호는 데코 레이트 되지 않은 데코 레이트 된 이름에만 적용 됩니다.

## <a name="remarks"></a>주의
이 열거형의 값은 다음 메서드에 전달 됩니다.

- [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)

- [IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)

- [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)

## <a name="requirements"></a>요구 사항
헤더: dia2.h

## <a name="see-also"></a>참고 항목
[열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)  
[IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)  
[IDiaSession::findFile](../../debugger/debug-interface-access/idiasession-findfile.md)  
[IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md)

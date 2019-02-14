---
title: IDiaSession::findFile | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- IDiaSession::findFile method
ms.assetid: a215dc21-b316-40d7-9923-55bfa014976b
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 59d36847416801965841d79b5be9e9a654487b96
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54986906"
---
# <a name="idiasessionfindfile"></a>IDiaSession::findFile
컴파일 대상 이름으로 소스 파일을 검색 합니다.  
  
## <a name="syntax"></a>구문  
  
```C++  
HRESULT findFile (   
   IDiaSymbol*           pCompiland,  
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSourceFiles** ppResult  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pCompiland`  
 [in] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 검색에 대 한 컨텍스트로 사용할 compiland를 나타내는 개체입니다. 이 매개 변수를 설정 `NULL` 모든 컴파일 대상에서 원본 파일을 찾아야 합니다.  
  
 `name`  
 [in] 검색할 소스 파일의 이름을 지정 합니다. 이 매개 변수를 설정 `NULL` 모든 소스 파일을 검색할 수 있습니다.  
  
 `option`  
 [in] 이름 검색에 적용할 비교 옵션을 지정 합니다. 값을 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 따로 또는 함께 사용할 수 있습니다.  
  
 `ppResult`  
 [out] 반환 된 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md) 원본 파일의 목록을 포함 하는 개체 검색 합니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="example"></a>예  
  
```C++  
IDiaEnumSourceFiles* pEnum;  
pSession->findFile( NULL, L"sourcefile.cpp", nsFNameExt, &pEnum );  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDiaEnumSourceFiles](../../debugger/debug-interface-access/idiaenumsourcefiles.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)
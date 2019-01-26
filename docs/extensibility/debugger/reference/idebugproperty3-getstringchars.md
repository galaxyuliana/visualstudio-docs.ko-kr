---
title: IDebugProperty3::GetStringChars | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- IDebugProperty3::GetStringChars
helpviewer_keywords:
- IDebugProperty3::GetStringChars
ms.assetid: 832c37f3-85cb-4227-8ab2-f27a80eafe90
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 6c70a2f9dd7e5ef52a0360ac59d995ddbd933c40
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54991205"
---
# <a name="idebugproperty3getstringchars"></a>IDebugProperty3::GetStringChars
이 속성을 사용 하 여 연결 된 문자열을 검색 하 고 사용자가 제공한 버퍼에 저장 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT GetStringChars(  
   ULONG  buflen,  
   WCHAR* rgString,  
   ULONG* pceltFetched  
);  
```  
  
```csharp  
int GetStringChars(  
   uint       buflen,   
   out string rgString,   
   out uint   pceltFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `buflen`  
 [in] 최대 문자 수는 사용자가 제공한 버퍼를 포함할 수 있습니다.  
  
 `rgString`  
 [out] 문자열을 반환합니다.  
  
 [C + +만] `rgString` 문자열의 유니코드 문자를 받는 버퍼에 대 한 포인터입니다. 이 버퍼 이상 이어야 합니다 `buflen` 크기에서 (바이트 아님) 문자입니다.  
  
 `pceltFetched`  
 [out] 여기서 실제로 버퍼에 저장 하는 문자 수가 반환 됩니다. (수 `NULL` c + +에서.)  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 C + +에서는 기울여야 버퍼 이상 인지 확인 `buflen` 자의 유니코드 문자입니다. 2 바이트 유니코드 문자는 참고 합니다.  
  
> [!NOTE]
>  C + +에서 반환된 된 문자열에는 null 종결 문자 포함 되지 않습니다. 주어진 경우 `pceltFetched` 문자열의 문자 수를 지정 합니다.  
  
## <a name="example"></a>예제  
 
```cpp  
CStringW RetrievePropertyString(IDebugProperty2 *pPropInfo)  
{  
    CStringW returnString = L"";  
    CComQIPtr<IDebugProperty3> pProp3 = pPropInfo->pProperty;  
    If (pProp3 != NULL) {  
        ULONG dwStrLen = 0;  
        HRESULT hr;  
        hr = pProp3->GetStringCharLength(&dwStrLen);  
        if (SUCCEEDED(hr) && dwStrLen > 0) {  
            ULONG dwRead;  
            CStrBufW buf(returnString,dwStrLen,CStrBuf::SET_LENGTH);  
            hr = pProp3->GetStringChars(dwStrLen,  
                                        reinterpret_cast<WCHAR*>(static_cast<CStringW::PXSTR>(buf)),  
                                        &dwRead);  
        }  
    }  
    return(returnString);
}
```    
  
## <a name="see-also"></a>참고 항목  
 [GetStringCharLength](../../../extensibility/debugger/reference/idebugproperty3-getstringcharlength.md)   
 [IDebugProperty3](../../../extensibility/debugger/reference/idebugproperty3.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
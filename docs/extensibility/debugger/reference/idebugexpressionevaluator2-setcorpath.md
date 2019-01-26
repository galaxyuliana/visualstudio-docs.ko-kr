---
title: IDebugExpressionEvaluator2::SetCorPath | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- SetCorPath
- IDebugExpressionEvaluator2::SetCorPath
ms.assetid: 27b614ff-7325-4f9b-8da4-61ee020c9410
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: fe7ab01b46350ad880e10c35c0b4236bbb31d24e
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54953606"
---
# <a name="idebugexpressionevaluator2setcorpath"></a>IDebugExpressionEvaluator2::SetCorPath
CLR (공용 언어 런타임) 디버거에서 로드 경로 설정 합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT SetCorPath(  
   LPCOLESTR pcstrCorPath  
);  
```  
  
```csharp  
int SetCorPath(  
   string pcstrCorPath  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pcstrCorPath`  
 [in] 디버거에서 로드 된 CLR에 대 한 경로입니다.  
  
## <a name="return-value"></a>반환 값  
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는이 메서드를 구현 하는 방법을 보여 줍니다는 **ExpressionEvaluatorPackage** 노출 하는 개체를 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md) 인터페이스입니다.  
  
```cpp  
STDMETHODIMP ExpressionEvaluatorPackage::SetCorPath(LPCOLESTR pcstrCorPath)  
{  
    VerifyInPtr(pcstrCorPath);  
    HRESULT hr = E_FAIL;  
  
    VBEECompilerSingleton *pVBEECompilerSingleton = VBEECompilerSingleton::Instance();  
  
    if (pVBEECompilerSingleton)  
    {  
        pVBEECompilerSingleton->LockEECompiler();  
  
        try  
        {  
            if (!m_pCompiler->FindEECompilerHost(pcstrCorPath, &m_pCompilerHost))  
            {  
                CComObject<CVBEECompilerHost> *pEECompilerHost;  
  
                if (SUCCEEDED(CComObject<CVBEECompilerHost>::CreateInstance(&pEECompilerHost)))  
                {  
                    pEECompilerHost->AddRef();  
                    pEECompilerHost->Init(pcstrCorPath);  
  
                    CComPtr<IVbCompilerHost> srpVBHost;  
                    HRESULT hr2 = pEECompilerHost->QueryInterface(IID_IVbCompilerHost, (void **)&srpVBHost);  
  
                    pEECompilerHost->Release();  
  
                    if (SUCCEEDED(hr2))  
                    {  
                        m_pCompiler->RegisterEECompilerHost(srpVBHost);  
                    }  
                }  
            }  
            else  
            {  
                hr = S_OK;  
            }  
  
            if (m_pCompiler->FindEECompilerHost(pcstrCorPath, &m_pCompilerHost))  
            {  
                ULONG cErrors = 0;  
                ULONG cWarnings = 0;  
  
                m_pCompiler->CompileToBound(m_pCompilerHost, &cErrors, &cWarnings, NULL);  
  
                // This needs to happen after bound  
                if (m_pCompilerHost->GetVbLibraryType() == TLB_AutoDetect)  
                {  
                    m_pCompilerHost->AutoSetVbLibraryType();  
                }  
  
                VSASSERT(m_pCompiler && m_pCompilerHost && m_pCompilerHost->GetIntrinsicSymbol(t_i4) != NULL, "Invalid state");  
  
                if (cErrors + cWarnings > 0)  
                {  
                    VSFAIL("Errors from mscorlib.dll and vb runtime!");                 
                    __leave;  
                }  
  
                hr = S_OK;  
            }  
            else  
            {  
                VSFAIL("FindCompilerHost shouldn't have failed!");  
            }  
        }  
        catch_hresult;  
  
        VSASSERT(m_pCompilerHost->GetComPlusProject()->GetCompState() >= CS_Bound, "Debugger mscorlib not in bound state");  
  
        pVBEECompilerSingleton->UnlockEECompiler();  
    }  
  
    return hr;  
}  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDebugExpressionEvaluator2](../../../extensibility/debugger/reference/idebugexpressionevaluator2.md)
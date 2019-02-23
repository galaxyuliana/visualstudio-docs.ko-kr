---
title: IDebugDocumentTextEvents2::onInsertText | Microsoft Docs
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- IDebugDocumentTextEvents2::OnInsertText
helpviewer_keywords:
- IDebugDocumentTextEvents2::onInsertText
ms.assetid: 6040181f-7288-4a42-953c-d23f74200431
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: a8eee7a9225a54bb5ca965845b66aaa9adcdbe05
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56700512"
---
# <a name="idebugdocumenttextevents2oninserttext"></a>IDebugDocumentTextEvents2::onInsertText
텍스트 문서에 삽입 되었음을 디버그 패키지에 알립니다.

## <a name="syntax"></a>구문

```cpp
HRESULT onInsert( 
   TEXT_POSITION pos,
   DWORD         dwNumToInsert
);
```

```csharp
int onInsert( 
   enum_TEXT_POSITION pos,
   uint               dwNumToInsert
);
```

#### <a name="parameters"></a>매개 변수
 `pos`

 [in] A [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md) 텍스트 삽입 된 위치를 나타내는 구조입니다.

 `dwNumToInsert`

 [in] 삽입 된 텍스트의 문자 수를 지정 합니다.

## <a name="return-value"></a>반환 값
 성공 하면 반환 `S_OK`고, 그렇지 않으면 오류 코드를 반환 합니다.

## <a name="see-also"></a>참고 항목
- [IDebugDocumentTextEvents2](../../../extensibility/debugger/reference/idebugdocumenttextevents2.md)
- [TEXT_POSITION](../../../extensibility/debugger/reference/text-position.md)
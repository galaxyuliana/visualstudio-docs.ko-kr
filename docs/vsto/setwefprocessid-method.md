---
title: SetWefProcessId 메서드
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 1352ccc9318061be4a2f9ad2da7d63715acd6721
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56603082"
---
# <a name="setwefprocessid-method"></a>SetWefProcessId 메서드
  웹 확장 프레임 워크 (WEF) 콘텐츠를 실행 하는 프로세스 식별자를 제공 합니다.

## <a name="syntax"></a>구문

```csharp
HRESULT SetWefProcessId(
    [in] DWORD dwProcessId
);
```

#### <a name="parameters"></a>매개 변수

|매개 변수|설명|
|---------------|-----------------|
|*dwProcessId*|WEF 콘텐츠 실행을 위해 사용할 프로세스 식별자입니다.|

## <a name="return-value"></a>반환 값
 메서드가 성공적으로 완료되었는지 여부를 나타내는 HRESULT 값입니다.

## <a name="remarks"></a>설명
 WEF 내용 프로세스가 만들어지면 있지만 WEF 내용을 실행 하기 전에이 메서드를 호출 해야 합니다.

 WEF 콘텐츠 프로세스에 디버거를 연결 하도록 개발 환경을 원한다 면 환경이 메서드의 구현에서이 작업을 수행 해야 합니다.

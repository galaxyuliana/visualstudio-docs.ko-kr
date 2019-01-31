---
title: '&lt;설명&gt; 요소 (ClickOnce 배포) | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- urn:schemas-microsoft-com:asm.v2#description
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- <description> element [ClickOnce deployment manifest]
ms.assetid: 18f6919e-a3ab-4942-a57d-167fabfac44e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 6c926da377688b1248daa01f015cda7914434a36
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55013901"
---
# <a name="ltdescriptiongt-element-clickonce-deployment"></a>&lt;설명&gt; 요소 (ClickOnce 배포)
셸에 표시를 만드는 데 사용 되는 응용 프로그램 정보를 식별 하 고 **프로그램 추가 / 제거** 제어판 항목입니다.  
  
## <a name="syntax"></a>구문  
  
```xml  
  
      <description   
   publisher   
   product  
   suiteName  
   supportUrl  
/>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `description` 요소는 필수이며 `urn:schemas-microsoft-com:asm.v1` 네임스페이스에 있습니다. 자식 요소가 없는 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`publisher`|필수 요소. Windows에서 아이콘 배치에 사용 되는 회사 이름을 식별 **시작** 메뉴와 **프로그램 추가 / 제거** 제어판에서 설치에 대 한 배포를 구성할 때 항목입니다.|  
|`product`|필수 요소. 전체 제품 이름을 식별합니다. Windows에 설치 되는 아이콘에 대 한 제목으로 사용 되는 **시작** 메뉴.|  
|`suiteName`|선택 사항입니다. 내에서 하위 폴더를 식별 하는 `publisher` 는 Windows에서 폴더 **시작** 메뉴.|  
|`supportUrl`|선택 사항입니다. 에 표시 되는 지원 URL을 지정 합니다 **프로그램 추가 / 제거** 제어판 항목입니다. 이 URL로 바로 가기는 Windows에서 응용 프로그램 지원을 위한 만들어져서 **시작** 메뉴에서 설치에 대 한 배포를 구성할 때.|  
  
## <a name="remarks"></a>주의  
 모든 배포 구성에서 description 요소가 필요 합니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제는 `description` 요소에는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 배포 매니페스트 합니다. 이 코드 예제는에 대해 제공 된 큰 예제의 일부 합니다 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md) 항목입니다.  
  
```xml  
<description   
  asmv2:publisher="My Company Name"  
  asmv2:product="My Application"  
  xmlns="urn:schemas-microsoft-com:asm.v1" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)
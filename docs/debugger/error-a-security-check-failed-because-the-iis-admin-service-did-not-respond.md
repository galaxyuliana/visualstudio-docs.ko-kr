---
title: '오류: IIS Admin Service 응답 하지 않아서 보안 검사를 실패 한 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.iis_not_responding
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugger, Web application errors
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 8ae97ae0594b06e9b35ac3bdd61eacf852968889
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851028"
---
# <a name="error-a-security-check-failed-because-the-iis-admin-service-did-not-respond"></a>오류: IIS 관리자 서비스에서 응답하지 않아서 보안 검사 실패
이 오류는 IIS 관리자 서비스에서 응답하지 않을 때 발생합니다. 일반적으로 이는 설치한 IIS에 문제가 있음을 나타냅니다. 먼저 **관리 도구**에서 **서비스** 도구를 사용하여 서비스가 실행 중인지 확인합니다.

### <a name="to-correct-this-error"></a>이 오류를 해결하려면

- 제어판의 **프로그램 추가 또는 제거**를 사용하여 IIS를 다시 설치합니다.

- 또는

- 제어판의 프로그램 추가/제거를 사용하여 컴퓨터에서 IIS를 제거합니다. IIS를 제거했는데도 문제가 해결되지 않으면 레지스트리에서 다음 키가 더 이상 표시되지 않는지 확인합니다.

    `HKEY_CLASSES_ROOT\CLSID\{A9E69610-B80D-11D0-B9B9-00A0C922E750}`

     또는

- 제어판의 관리 도구를 사용하여 IIS 관리자 서비스를 사용하지 않도록 설정합니다. 이렇게 하면 사용자의 컴퓨터에서 IIS를 사용할 수 없습니다.

     이 세 단계 중 하나를 수행한 후에 컴퓨터를 다시 시작합니다.

     자세한 내용은 IIS 설명서를 참조하십시오.

## <a name="see-also"></a>참고 항목
- [웹 애플리케이션 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
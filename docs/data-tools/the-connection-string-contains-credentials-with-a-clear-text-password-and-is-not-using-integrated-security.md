---
title: 연결 문자열에 일반 텍스트 암호가 있는 자격 증명이 포함되어 있으며 통합 보안을 사용하지 않습니다.
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 501d85af-92e0-4471-b280-8a59c0688575
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: b270290c948807ff0f66d3d142312245475cd33c
ms.sourcegitcommit: 50f0c3f2763a05de8482b3579026d9c76c0e226c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/09/2019
ms.locfileid: "65460601"
---
# <a name="the-connection-string-contains-credentials-with-a-clear-text-password-and-is-not-using-integrated-security"></a>연결 문자열에 일반 텍스트 암호가 있는 자격 증명이 포함되어 있으며 통합 보안을 사용하지 않습니다.

중요한 정보가 포함된 연결 문자열을 현재 DBML 파일 및 애플리케이션 구성 파일에 저장하시겠습니까?  중요한 정보를 포함하지 않고 연결 문자열을 저장하려면 **아니요**를 클릭하세요.

연결 문자열에 포함된 암호와 같이 중요한 정보가 들어 있는 데이터 연결을 사용하는 경우 연결 문자열에 중요한 정보를 포함시키거나 제외시켜 프로젝트의 DBML 파일 및 애플리케이션 구성 파일에 저장하는 옵션이 제공됩니다.

> [!WARNING]
> **연결** 속성의 **애플리케이션 설정** 속성을 명시적으로 **False**로 설정하면 DBML 파일에 암호가 추가됩니다.

## <a name="save-options"></a>저장 옵션

- 중요 한 정보를 사용 하 여 연결 문자열을 저장 하려면 **예**합니다.

   연결 문자열이 애플리케이션 설정대로 저장됩니다. 연결 문자열에는 중요한 정보가 일반 텍스트로 포함됩니다. DBML 파일에는 중요한 데이터가 포함되지 않습니다.

- 중요 한 정보가 없는 연결 문자열을 저장 하려면 선택 **No**합니다.

   연결 문자열이 애플리케이션 설정대로 저장되지만 암호는 포함되지 않습니다.

## <a name="see-also"></a>참고자료

- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md)
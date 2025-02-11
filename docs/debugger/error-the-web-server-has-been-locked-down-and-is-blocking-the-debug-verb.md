---
title: '오류: 웹 서버가 잠겨 있기 DEBUG 동사를 차단 하 고 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.webdbg_debug_verb_blocked
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
ms.openlocfilehash: 22a564da1de8a7f375209ff4c02236a3e2baca8f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62850664"
---
# <a name="error-the-web-server-has-been-locked-down-and-is-blocking-the-debug-verb"></a>오류: 웹 서버가 잠겨 있어 DEBUG 동사를 차단함
IIS 잠금 도구가 실행되었고 URLScan이 설치되어 활성화되어 있기 때문에 웹 애플리케이션 또는 XML Web services를 한 단계씩 실행하지 못했습니다. 이 상태가 되면 IIS에서 DEBUG 동사를 받을 수 없습니다.

 URLScan은 IIS 잠금 도구와 함께 작동하는 보안 도구로서, IIS 웹 사이트 관리자는 이 도구를 사용하여 필요하지 않은 기능을 끄고 서버에서 처리하는 HTTP 요청 형식을 제한할 수 있습니다. URLScan 보안 도구를 사용하면 특정 HTTP 요청을 차단하여 위험한 요청이 서버로 들어와 서버가 손상되는 것을 방지할 수 있습니다.

 애플리케이션이 Windows Server 2003의 IIS 6.0에서 실행될 경우 IIS 6.0에서 IIS 잠금 도구와 동일한 기능을 제공하므로 이 도구를 실행할 필요가 없습니다.

### <a name="to-enable-debugging-on-a-web-server-with-urlscan-installed"></a>URLScan이 설치된 웹 서버에서 디버깅을 사용하려면

1. Urlscan.ini 파일을 찾습니다. 일반적으로 이 파일은 다음 디렉터리에 있습니다.

     C:\WINNT\System32\Inetsrv\urlscan

2. 이 파일의 복사본을 만들어 이름을 **Urlscan.old**로 지정합니다.

3. 메모장이나 원하는 텍스트 편집기를 사용하여 원본 Urlscan.ini 파일을 엽니다.

4. Urlscan.ini 파일에서 [AllowVerbs] 섹션을 찾습니다. [AllowVerbs] 섹션에 DEBUG를 추가합니다. [AllowVerbs] 섹션에 ;DEBUG가 있으면 이 동사를 주석으로 처리하는 세미콜론을 제거합니다.

5. [DenyVerbs] 섹션을 찾습니다. [DenyVerbs] 섹션에 DEBUG가 있으면 제거합니다.

6. 파일을 저장합니다.

7. 서버를 다시 시작하거나 IIS를 다시 시작합니다.

## <a name="see-also"></a>참고 항목
- [웹 애플리케이션 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)
- [오류: 요청한 리소스를 웹 서버에서 찾지 못했습니다.](../debugger/error-the-web-server-could-not-find-the-requested-resource.md)
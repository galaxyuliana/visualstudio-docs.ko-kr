---
title: 프록시 권한 필요 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 9
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: b55dba438280fc4579fe15bd2a423d323c38abf6
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "54767287"
---
# <a name="proxy-authorization-required"></a>프록시 권한 필요
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

  
이 오류는 대개 사용자가 프록시 서버를 통해 Visual Studio Online에 연결했는데 프록시 서버에서 호출을 차단하는 경우 발생합니다. Visual Studio Online은 사용자의 IDE 로그인 상태를 유지하는 데 사용됩니다.  
  
## <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   Visual Studio를 다시 시작합니다. 프록시 인증 대화 상자가 나타납니다. 대화 상자에서 자격 증명을 입력합니다.  
  
-   위의 단계를 수행해도 문제가 해결되지 않으면 프록시 서버에서 http://go.microsoft.com 주소가 아닌 *.visualStudio.com 주소에 대한 자격 증명을 입력하라는 메시지를 표시하기 때문일 수 있습니다. 이러한 서버에 대해 다음을 허용 목록에 포함하여 Visual Studio에서 모든 로그인 시나리오의 차단을 해제해야 합니다.  
  
    -   *.windows.net  
  
    -   *.microsoftonline.com  
  
    -   *.visualstudio.com  
  
    -   *.microsoft.com  
  
    -   *.live.com  
  
-   그렇지 않은 경우 제거할 수 있습니다 합니다 http://go.microsoft.com 프록시 인증 대화 상자가 모두에 대 한 표시 되도록 허용 목록에서 주소를 http://go.microsoft.com 주소 및 Visual Studio를 다시 시작할 때 서버 끝점입니다.  
  
-   또는  
  
-   프록시에 기본 자격 증명을 사용하려는 경우 다음 작업을 수행하면 됩니다.  
  
    1.   **%ProgramFiles%\Microsoft Visual Studio 14.0\Common7\IDE** (또는 **%ProgramFiles(x86)%\Microsoft Visual Studio 14.0\Common7\IDE**)에서 devenv.exe.config(devenv.exe 구성 파일)를 찾습니다.  
  
    2.  구성 파일에서 `<system.net>` 블록을 찾아 다음 코드를 추가합니다.  
  
        ```xml  
        <defaultProxy enabled="true" useDefaultCredentials="true">  
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>  
        </defaultProxy>  
  
        ```  
  
         `proxyaddress="<http://<yourproxy:port#>`에는 네트워크의 올바른 프록시 주소를 삽입해야 합니다.  
  
-   또는  
  
-   [이 게시물](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) 의 지침에 따라 프록시를 사용할 수 있는 코드를 추가할 수도 있습니다.

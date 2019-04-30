---
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.openlocfilehash: d89dbc0b752c2b8c538ec53769c166b6edbd802f
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62902884"
---
1. 원격 컴퓨터의 찾기 및 시작 합니다 **원격 디버거** 에서 합니다 **시작** 메뉴. 
   
   원격 컴퓨터에서 관리 권한이 없으면 마우스 오른쪽 단추로 클릭 합니다 **원격 디버거** 앱을 선택 **관리자 권한으로 실행**합니다. 이 고, 그렇지만 정상적으로 시작 합니다.

   서로 다른 버전의 있을 수 있습니다 *msvsmon.exe* 에 *x64*를 *x32*, 또는 기타 폴더입니다. 앱 디버그에 필요한 버전을 시작 해야 합니다. 
   
1. 처음으로 원격 디버거를 시작, 구성 하기 전에 합니다 **원격 디버깅 구성** 대화 상자가 나타납니다.  
  
    ![원격 디버거 구성](../media/remotedebuggerconfwizardpage.png "원격 디버거 구성")  
  
1. Windows 웹 서비스 API 설치 되지 않은 경우, Windows Server 2008 R2 에서만 발생 함을 선택 합니다 **설치** 단추입니다.  
  
1. 원격 도구를 사용 하려면 하나 이상의 네트워크 형식을 선택 합니다. 컴퓨터가 도메인을 통해 연결된 경우 첫 번째 항목을 선택해야 합니다. 컴퓨터가 작업 그룹 또는 홈 그룹을 통해을 연결 하는 경우 적절 하 게 두 번째 또는 세 번째 항목을 선택 합니다.  
  
1. 선택 **원격 디버깅 구성** 방화벽을 구성 하 고 원격 디버거를 시작 합니다.  
  
1. 구성이 완료 되 면 합니다 **원격 디버거** 창이 나타납니다.
  
    ![원격 디버거 창](../media/remotedebuggerwindow.png "원격 디버거 창")
  
    원격 디버거 연결 대기 중 이제입니다. 서버 이름을 사용 하 고 포트 번호를 Visual Studio에서 원격 연결 구성 설정에 게 표시 합니다.  
  
원격 디버거를 중지 하려면 선택 **파일** > **종료**합니다. 다시 시작할 수 있습니다 합니다 **시작** 메뉴 또는 명령줄에서:  
  
```cmd
<Remote debugger installation directory>\msvsmon.exe
```

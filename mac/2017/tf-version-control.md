---
title: TFVC(Team Foundation 버전 제어)
description: TFVC(Team Foundation 버전 제어)를 사용하여 Team Foundation Server 또는 Azure DevOps Services에 연결.
author: conceptdev
ms.author: crdun
ms.date: 09/05/2018
ms.topic: article
ms.technology: vs-ide-general
ms.assetid: 52D3D26A-4D01-4FD1-AAA1-AE7D7BD39746
ms.openlocfilehash: 1d560e3fd383e3db19c664bf027470c8da224fd2
ms.sourcegitcommit: 509fc3a324b7748f96a072d0023572f8a645bffc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58857803"
---
# <a name="connecting-to-team-foundation-version-control"></a>Team Foundation 버전 제어에 연결

> [!NOTE]
> Team Foundation 버전 제어 지원은 현재 미리 보기 상태이며, 일부 기능은 아직 완전히 작동하지 않습니다. 모든 문제에 대한 피드백을 [개발자 커뮤니티](https://developercommunity.visualstudio.com/spaces/41/index.html)에 올려주시면 감사하겠습니다. 아직 변경의 여지가 많이 있습니다.

Azure Repos에서는 다음과 같은 두 가지 버전 제어 모델을 제공합니다. 분산된 버전 제어인 Git 및 중앙 집중식 제어인 TFVC(Team Foundation 버전 제어). 이 문서에서는 Mac용 Visual Studio에서 TFVC를 사용하는 방법에 대한 개요와 그 시작점을 제공합니다.

## <a name="requirements"></a>요구 사항

* Visual Studio Community, Professional 또는 Mac용 Enterprise 버전 7.5 이상.
* Azure DevOps Services 또는 Team Foundation Server 2013 이상.
* Team Foundation 버전 제어를 사용하도록 구성된 Azure DevOps Services 또는 Team Foundation Server의 프로젝트.

## <a name="installation"></a>설치

Mac용 Visual Studio의 메뉴에서 **Visual Studio > 확장**을 선택합니다. **갤러리** 탭에서 **버전 제어 > TFS 및 VSTS용 Team Foundation 버전 제어**를 선택하고 **설치**를 클릭합니다.

![확장 관리자](media/tfvc-install.png)

표시되는 메시지에 따라 확장을 설치합니다. 설치가 완료되면 IDE를 다시 시작합니다.

## <a name="updating-the-extension"></a>확장 업데이트

TFVC 확장에 대한 업데이트는 정기적으로 이루어집니다. 업데이트에 액세스하려면 메뉴에서 **Visual Studio > 확장...** 을 선택하고 **업데이트** 탭을 선택합니다. 목록에서 확장을 선택하고 **업데이트** 단추를 누릅니다.

![업데이트를 표시하는 확장 관리자](media/tfvc-update.png)

다음 대화 상자에서 **설치**를 눌러 이전 패키지를 제거하고 새 패키지를 설치합니다.

## <a name="using-the-add-in"></a>추가 기능 사용

확장이 설치되면 **버전 제어 > TFS/Azure DevOps > 원격 리포지토리에서 열기** 메뉴 항목을 선택합니다.

![확장을 여는 메뉴 항목](media/tfvc-source-control-explorer-devops.png)

VSTS 또는 Team Foundation Server를 선택하여 시작하고 **계속**을 누릅니다.

![서버와 연결](media/tfvc-choose-server-type-devops.png)

### <a name="azure-repos-authentication"></a>Azure Repos 인증

Azure Repos에서 호스팅되는 프로젝트를 선택하면 Microsoft 계정 세부 정보를 입력하라는 메시지가 표시됩니다.

![Azure Repos를 사용하여 연결](media/tfvc-vsts-login.png)

### <a name="tfs-authentication"></a>TFS 인증

TFS에 연결하려면 서버 세부 정보와 계정 자격 증명을 입력합니다. NTLM 인증을 사용할 도메인을 입력하고 기본 인증을 사용하려면 비워 둡니다. **서버 추가**를 선택합니다.

![TFS 서버에 로그인](media/tfvc-login.png)

## <a name="selecting-a-project"></a>프로젝트 선택

인증에 성공하면 **소스 제어에서 열기** 대화 상자에서 계정과 연결된 리포지토리 목록을 볼 수 있습니다.

![표시되는 프로젝트가 있는 소스 제어 대화 상자에서 열기](media/tfvc-vsts-projects.png)

이 대화 상자는 다음 노드로 구성됩니다.

- Azure DevOps 조직 또는 컬렉션 - 로그인할 때 사용하는 Microsoft 계정에 연결된 모든 조직이 표시됩니다.
- 프로젝트 - 각 조직 또는 컬렉션에 많은 수의 프로젝트가 포함될 수 있습니다. 프로젝트는 소스 코드, 작업 항목 및 자동화된 빌드가 호스팅되는 위치입니다.

이 시점에서 프로젝트 또는 조직의 이름으로 검색하고 필터링할 수 있습니다.

### <a name="adding-a-new-server"></a>새 서버 추가

새 서버를 목록에 추가하려면 **소스 제어에서 열기** 대화 상자에서 **호스트 추가** 단추를 누릅니다.

![새 서버를 목록에 추가하는 강조 표시된 추가 단추](media/tfvc-add-new-server.png)

목록에서 공급자를 선택하고 자격 증명을 입력합니다.

![소스 제어 공급자에 대한 옵션을 표시하는 대화 상자](media/tfvc-add-new-creds-devops.png)

## <a name="creating-a-new-workspace"></a>새 작업 영역 만들기

프로젝트를 작업을 시작하려면 _작업 영역_이 있어야 합니다. 작업 영역이 아직 없는 경우 **소스 제어에서 열기** 대화 상자의 **작업 영역** 콤보 상자에서 작업 영역을 만들 수 있습니다.

![새 작업 영역 콤보 상자 옵션 만들기](media/tfvc-create-new-workspace.png)

새 작업 영역의 로컬 경로를 설정하고 **작업 영역 만들기**를 선택합니다.

![새 작업 영역의 이름 및 로컬 경로 입력](media/tfvc-local-workspace.png)

## <a name="using-the-source-code-explorer"></a>소스 코드 탐색기 사용

작업 영역을 만들고 프로젝트를 매핑하면 _소스 코드 탐색기_를 사용하여 작업을 시작할 수 있습니다.

소스 코드 탐색기를 열려면 **버전 제어 > TFS/Azure DevOps > 소스 제어 탐색기** 메뉴 항목을 선택합니다.

소스 코드 탐색기를 사용하면 매핑된 모든 프로젝트, 해당 파일 및 폴더를 탐색할 수 있습니다. 또한 다음과 같은 모든 기본 소스 제어 작업을 수행할 수 있습니다.

- 최신 버전 가져오기
- 특정 버전 가져오기
- 파일 체크 인 및 체크 아웃
- 파일 잠금 및 잠금 해제
- 추가, 삭제 및 파일 이름 바꾸기
- 기록 보기
- 변경 내용 비교.

이러한 작업 중 대부분은 프로젝트의 컨텍스트 작업을 통해 수행할 수 있습니다.

![프로젝트에 대한 바로 가기 메뉴 작업](media/tfvc-sourcecode-actions.png)

## <a name="managing-workspaces"></a>작업 영역 관리

[작업 영역 만들기](#creating-a-new-workspace) 섹션에서 설명한 대로 작업 영역을 아직 만들지 않은 경우 소스 코드 탐색기는 비어 있습니다.

![빈 소스 코드 탐색기](media/tfvc-setup-empty-sce.png)

로컬 작업 영역으로 원격 프로젝트를 설정하려면 다음 단계를 수행합니다.

1. 콤보 상자에서 **서버**를 선택합니다.
1. "작업 공간 없음" 및 로컬 경로가 "매핑되지 않음"을 참고합니다. **매핑되지 않음** 링크를 선택하여 **새 작업 영역 만들기** 대화 상자를 표시합니다.
1. 작업 영역의 이름을 지정한 후 **작업 폴더 추가**를 클릭하여 컴퓨터의 로컬 폴더에 프로젝트를 매핑합니다.

    ![기본 옵션을 표시하는 새 작업 영역 대화 상자 만들기](media/tfvc-workspace1.png)

1. "$" 폴더를 선택하여 서버의 모든 프로젝트를 동일한 작업 영역에 매핑하거나 개별 프로젝트를 선택하고 **확인**을 클릭합니다.

    ![모든 프로젝트를 표시하는 폴더 대화 상자 찾아보기](media/tfvc-workspace2.png)

1. 프로젝트를 매핑하려는 로컬 머신의 위치를 선택하고 **폴더 선택**을 클릭합니다.
1. **확인**을 눌러 새 작업 영역의 세부 정보 확인

    ![작업 폴더가 추가된 새 작업 영역 대화 상자 만들기](media/tfvc-workspace3.png)

작업 영역이 설정되면 소스 코드 탐색기에서 **작업 영역 관리** 단추를 클릭하여 작업 영역을 변경하거나 제거할 수 있습니다.

![작업 영역 관리](media/tfvc-workspace4.png)

## <a name="troubleshooting"></a>문제 해결

### <a name="problems-using-basic-authentication"></a>기본 인증 사용 문제

다음 옵션을 사용하여 서버를 인증할 수 있습니다.

- Oauth
- Basic
- Ntlm

기본 인증을 사용하려면 다음 단계에 따라 Azure DevOps Services에서 **대체 인증 자격 증명**을 활성화해야 합니다.

1. 소유자로 Azure DevOps 조직에 로그인합니다(https://dev.azure.com/{organization}/{project}).

2. 조직 도구 모음에서 기어 아이콘을 선택하고 **정책**을 선택합니다.

    ![선택한 정책 설정 옵션](media/tfvc-auth2.png)

3. 애플리케이션 연결 설정을 검토합니다. 보안 정책에 따라 다음 설정을 변경합니다.

    ![선택한 정책 설정 옵션](media/tfvc-auth.png)

### <a name="i-do-not-see-anything-in-tfvc"></a>TFVC에 아무것도 표시되지 않음

개발 머신에서 TFVC(Team Foundation 버전 제어)를 설정하려면 [작업 영역 관리](#managing-workspaces) 섹션에 설명된 대로 작업 영역을 **만들어야** 합니다.

소스 제어 탐색기에서 **작업 영역 관리** 단추를 누릅니다. 프로젝트를 개발 머신의 폴더에 매핑하는 단계를 수행합니다.

### <a name="i-do-not-see-any--all-of-my-projects"></a>내 프로젝트 중 일부/전부가 표시되지 않음

인증 후 프로젝트 목록을 확인해야 합니다. 기본적으로 TFS 프로젝트만 표시됩니다. 다른 형식의 프로젝트를 보려면 "모든 프로젝트 보기" 상자를 선택합니다.

올바른 권한이 없는 경우 서버에 있는 프로젝트가 표시되지 않습니다.

#### <a name="i-am-getting-the-error-cannot-create-the-workspace-please-try-again"></a>"작업 영역을 만들 수 없습니다. 다시 시도하세요."라는 오류 메시지가 나타납니다.

[새 작업 영역 만들기](#creating-a-new-workspace)를 수행할 때 다음 조건이 충족되었는지 확인해야 합니다.

- 작업 영역 이름에 잘못된 문자를 사용하지 마세요.
- 이름은 64자 미만이어야 합니다.
- 로컬 경로는 다른 작업 영역에서 사용할 수 없습니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio를 사용하여 TFVC에서 코드 개발 및 공유(Windows에서)](/azure/devops/repos/tfvc/share-your-code-in-tfvc-vs)
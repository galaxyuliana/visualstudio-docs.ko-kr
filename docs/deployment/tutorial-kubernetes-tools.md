---
title: Kubernetes 도구 자습서 | Microsoft Docs
ms.date: 06/08/2018
ms.topic: conceptual
author: ghogen
ms.author: ghogen
manager: jillfra
ms.workload:
- azure
ms.openlocfilehash: c6a0ba1f44d9e6d9cc0dbcce03af2705e370cbb6
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54965461"
---
# <a name="get-started-with-visual-studio-kubernetes-tools"></a>Visual Studio Kubernetes 도구 시작

Visual Studio Kubernetes 도구 도움말 Kubernetes를 대상으로 하는 컨테이너 화 된 응용 프로그램의 개발을 간소화 합니다. Visual Studio Dockerfile 및 Helm 차트와 같은 Kubernetes 배포를 지 원하는 데 필요한 코드와 구성 파일을 자동으로 만들 수 있습니다. Azure 개발 공간을 사용 하 여 라이브 Azure Kubernetes Service (AKS) 클러스터에서 코드를 디버그 하거나에서 AKS 클러스터에 직접 게시할 수 Visual Studio 내에서.

이 자습서는 Visual Studio를 사용 하 여 Kubernetes를 지 원하는 프로젝트에 추가 하 고 AKS에 게시를 다룹니다. 사용 하 여 주로 관심이 있다면 [Azure 개발 공간](http://aka.ms/get-azds) 를 디버그 하 고 AKS에서 실행 중인 프로젝트를 테스트 하 게 이동할 수 있습니다 합니다 [Azure 개발 공간 자습서](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio) 대신 합니다.

## <a name="prerequisites"></a>전제 조건

이 새로운 기능을 활용 하려면 다음이 필요 합니다.

- 최신 버전의 [Visual Studio 2017](https://visualstudio.microsoft.com/download) 사용 하 여 합니다 *ASP.NET 및 웹 개발* 워크 로드.

- 합니다 [Visual Studio 용 Kubernetes 도구](https://aka.ms/get-vsk8stools), 별도 다운로드로 제공 합니다.

- [Windows 용 docker](https://store.docker.com/editions/community/docker-ce-desktop-windows) 개발 워크스테이션에 설치 된 (즉, 여기서 Visual Studio를 실행), Docker 이미지를 빌드 하려는 경우 로컬에서 실행 되는 Docker 컨테이너를 디버그 하거나 AKS에 게시 합니다. (Docker *되지* 빌드 및 Azure 개발 공간을 사용 하 여 AKS에서 Docker 컨테이너를 디버깅 하는 데 필요한.)

- Visual Studio에서 AKS에 게시 하려는 경우 (*되지* Azure 개발 공간을 사용 하 여 AKS에서 디버깅 하는 데 필요한):

    1.  합니다 [AKS 게시 도구](https://aka.ms/get-vsk8spublish), 별도 다운로드로 제공 합니다.

    1.  Azure Kubernetes Service 클러스터입니다. 자세한 내용은 [AKS 클러스터를 만들](/azure/aks/kubernetes-walkthrough-portal#create-aks-cluster)합니다. 해야 [클러스터에 연결](/azure/aks/kubernetes-walkthrough#connect-to-the-cluster) 개발용 워크스테이션에서.

    1.  Helm CLI 개발 워크스테이션에 설치 합니다. 자세한 내용은 참조 [Helm 설치](https://github.com/kubernetes/helm/blob/master/docs/install.md)합니다.

    1.  Helm을 사용 하 여 AKS 클러스터에 대해 구성 된 `helm init` 명령입니다. 이 작업을 수행 하는 방법에 대 한 자세한 내용은 참조 하세요. [Helm을 구성 하는 방법](/azure/aks/kubernetes-helm#configure-helm)합니다.

## <a name="create-a-new-kubernetes-project"></a>새 Kubernetes 프로젝트 만들기

설치 된 적절 한 도구를 만든 후 Visual Studio를 시작 하 고 새 프로젝트를 만듭니다. 아래 **클라우드**를 선택 합니다 **Kubernetes에 대 한 컨테이너 응용 프로그램** 프로젝트 형식. 이 프로젝트 형식을 선택 하 고 선택 **확인**합니다.

![새 Kubernetes 앱 프로젝트 만들기의 스크린샷](media/k8s-tools-new-k8s-app.png)

다음 어떤 유형의 ASP.NET Core 웹 응용 프로그램 만들기를 선택할 수 있습니다. 선택할 **웹 응용 프로그램** 선택한 **확인**합니다. 일반적인 **Docker 지원 활성화** 이 대화 상자에서 옵션이 표시 되지 않습니다.  Docker 지원 Kubernetes에 대 한 컨테이너 응용 프로그램에 대 한 기본으로 사용 됩니다.

![웹 앱 선택 스크린샷](media/k8s-tools-web-app-selection-screen.png)

## <a name="add-kubernetes-support-to-an-existing-project"></a>Kubernetes를 지 원하는 기존 프로젝트에 추가

또는 Kubernetes를 지 원하는 기존 ASP.NET Core 웹 응용 프로그램 프로젝트에 추가할 수 있습니다. 이렇게 하려면 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가** > **컨테이너 오 케 스트레이 터 지원**합니다.

![스크린 샷의 추가 컨테이너 오 케 스트레이 터 메뉴 항목](media/k8s-tools-add-container-orchestrator.png)

대화 상자에서 "Kubernetes/Helm"를 선택 하 고 선택 **확인**합니다.

![대화 상자 스크린 샷의 추가 컨테이너 오 케 스트레이 터](media/k8s-tools-add-container-orchestrator-dialog-box.PNG)

## <a name="what-visual-studio-creates-for-you"></a>Visual Studio는를 만듭니다

새로 만든 후 **Kubernetes에 대 한 컨테이너 응용 프로그램** Kubernetes에 배포에 도움이 되는 일부 추가 파일 프로젝트에서 프로젝트 또는 기존 프로젝트에 Kubernetes 컨테이너 오 케 스트레이 터 지원 추가 표시 합니다.

![솔루션 탐색기 스크린샷 컨테이너 오 케 스트레이 터 지원을 추가한 후](media/k8s-tools-solution-explorer.png)

추가 된 파일이 다음과 같습니다.

- Dockerfile이 웹 응용 프로그램을 호스트 하는 컨테이너 이미지는 Docker를 생성할 수 있는 합니다. 알 수 있듯이 Visual Studio 도구는 디버깅 및 Kubernetes에 배포 하는 경우이 Dockerfile을 활용 합니다. Docker 이미지를 사용 하 여 직접 작업 하려는 경우에 Dockerfile을 마우스 오른쪽 단추로 클릭 합니다. 고 선택할 수 있습니다 **Docker 이미지 빌드**합니다.

   ![스크린 샷의 빌드 Docker 이미지 옵션](media/k8s-tools-build-docker-image.png)

- Helm 차트 및 *차트* 폴더입니다. 이 yaml 파일을 Kubernetes에 배포 하는 데 사용할 수 있는 응용 프로그램에 대 한 Helm 차트를 구성 합니다. Helm에 대 한 자세한 내용은 참조 하세요. [ https://www.helm.sh ](https://www.helm.sh)합니다.

- *azds.yaml*. Azure Kubernetes Service에서 신속 하 고 반복 디버깅 환경을 제공 하는 Azure 개발 공간에 대 한 설정을 포함 합니다. 자세한 내용은 참조 하세요 [Azure 개발 공간 설명서](https://docs.microsoft.com/azure/dev-spaces/azure-dev-spaces)합니다.

## <a name="publish-to-azure-kubernetes-service-aks"></a>AKS (Azure Kubernetes Service)에 게시

현재 위치에서 이러한 모든 파일을 사용 하 여 항상 있는 것 처럼 작성 하 고 응용 프로그램 코드를 디버그 하려면 Visual Studio IDE를 사용할 수 있습니다. 사용할 수도 있습니다 [Azure 개발 공간](http://aka.ms/get-azds) 신속 하 게 실행 하 고 AKS 클러스터에서 라이브 실행 코드를 디버깅 합니다. 자세한 내용은 참조는 [Azure 개발 공간 자습서](https://docs.microsoft.com/azure/dev-spaces/get-started-netcore-visualstudio)

만든 후, 원하는 방식으로 실행 되는 코드가 AKS 클러스터에 Visual Studio에서 직접 게시할 수 있습니다.

이렇게 하려면 먼저는 설치한 모든 항목에 설명 된 대로 다시 확인 하는 [필수 구성 요소](#prerequisites) AKS에 게시에 대 한 항목 아래에 있는 섹션 및 링크에 지정 된 모든 명령줄 단계를 실행 합니다. 그런 다음 컨테이너 이미지를 ACR Azure Container Registry ()를 게시 하는 게시 프로필을 설정 합니다. 다음 AKS는 ACR에서 컨테이너 이미지를 풀 하 고 클러스터에 배포할 수 있습니다.

1. **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 하 *프로젝트* 선택한 **게시**합니다.

   ![메뉴 항목 게시 스크린 샷](media/k8s-tools-publish-project.png)

2. 에 **게시** 화면에서 선택 **Container Registry** 게시와 대상 및 지시에 따라 컨테이너 레지스트리를 선택 합니다. 컨테이너 레지스트리를 아직 없는 경우 선택할 **새 Azure Container Registry 만들기** Visual Studio에서 만들어야 합니다. 자세한 내용은 [Azure Container Registry에 컨테이너를 게시](#publish-your-container-to-azure-container-registry)합니다.

   ![게시 대상 화면 선택 스크린샷](media/k8s-tools-publish-to-acr.png)

3. 솔루션 탐색기에서 다시 마우스 오른쪽 단추로 클릭 하 *솔루션* 클릭 **Azure AKS에 게시**합니다.

   ![스크린 샷의 게시할 Azure AKS 메뉴 항목](media/k8s-tools-publish-solution.png)

4. ACR과 함께 방금 만든 프로필을 게시, 구독 및 AKS 클러스터를 선택 합니다. 그런 다음 **확인**을 클릭합니다.

   ![스크린 샷의 게시할 AKS 화면](media/k8s-tools-publish-to-aks.png)

   로 이동 합니다 **AKS Azure에 게시** 화면.

5. 선택 된 **Helm 구성** Helm 차트를 서버에 설치 하는 데 사용 된 명령줄을 업데이트 하려면 연결 합니다.

   ![링크 구성 Helm 스크린 샷](media/k8s-tools-configure-helm.png)

   명령줄을 업데이트 하는 것은 사용자 지정 명령줄 인수 예: 다른 Kubernetes 컨텍스트 또는 차트 이름 지정 하려는 경우에 유용 합니다.

   ![스크린샷의 Helm 구성 화면](media/k8s-tools-helm-configure-screen.png)

6. 배포할 준비가 되 면 클릭 합니다 **게시** AKS에 응용 프로그램을 게시 하는 단추입니다.

   ![Azure AKS 화면에 게시의 스크린샷](media/k8s-tools-publish-screen.png)

지금까지 이제 모든 Kubernetes 앱 개발을 위한 Visual Studio의 모든 기능을 사용할 수 있습니다.

## <a name="next-steps"></a>다음 단계

에 대해 자세히 알아보려면 Azure에서 Kubernetes 개발 읽어 합니다 [AKS 설명서](/azure/aks)합니다.

에 대해 자세히 알아보려면 Azure 개발 공백을 읽으면는 [Azure 개발 공간 설명서](http://aka.ms/get-azds)

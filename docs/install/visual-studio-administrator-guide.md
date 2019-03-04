---
title: Visual Studio 관리자 가이드
titleSuffix: ''
description: 엔터프라이즈 환경에 Visual Studio를 배포하는 방법을 자세히 알아봅니다.
ms.date: 05/29/2018
ms.custom: seodec18
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
ms.assetid: 4af353f5-6cfd-4ebe-bcfb-f42306e451a0
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: adfebd52f477328193a97a8fdb91300eef215fd7
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56710112"
---
# <a name="visual-studio-2017-administrator-guide"></a>Visual Studio 2017 관리자 가이드

엔터프라이즈 환경에서는 일반적으로 시스템 관리자가 네트워크 공유 또는 시스템 관리 소프트웨어를 사용하여 최종 사용자에게 설치를 배포합니다. Visual Studio 설치 엔진은 엔터프라이즈 배포를 지원하여 시스템 관리자가 네트워크 설치 위치를 만들고, 설치 기본값을 미리 구성하고, 설치 프로세스에서 제품 키를 배포하고, 출시 후 제품 업데이트를 관리할 수 있도록 구성되었습니다. 이 관리자 가이드에서는 네트워크 환경의 엔터프라이즈 배포에 대한 시나리오 기반 지침을 제공합니다.

## <a name="deploy-visual-studio-2017-in-an-enterprise-environment"></a>엔터프라이즈 환경에 Visual Studio 2017 배포

각 대상 컴퓨터가 [최소 설치 요구 사항](/visualstudio/productinfo/vs2017-system-requirements-vs)을 충족하면 클라이언트 워크스테이션에 Visual Studio 2017을 배포할 수 있습니다. System Center 같은 소프트웨어를 통해 배포하든 아니면 배치 파일을 통해 배포하든 대개 다음 단계를 수행하게 됩니다.

1. 네트워크 위치에 [Visual Studio 제품 파일이 포함된 네트워크 공유를 만듭니다](create-a-network-installation-of-visual-studio.md).

2. 설치하려는 [워크로드 및 구성 요소 선택](workload-and-component-ids.md)

3. 기본 설치 옵션이 포함된 [지시 파일을 만듭니다](automated-installation-with-response-file.md). 또는 명령줄 매개 변수를 사용하여 설치를 제어하는 [설치 스크립트를 빌드](use-command-line-parameters-to-install-visual-studio.md)합니다.

4. 필요에 따라 설치 스크립트의 일부로 [볼륨 라이선스 제품 키를 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)하여 사용자가 소프트웨어를 별도로 활성화할 필요가 없도록 합니다.

5. 네트워크 레이아웃을 업데이트하여 [제품 업데이트가 최종 사용자에게 전달되는 시점을 제어](controlling-updates-to-visual-studio-deployments.md)합니다.

6. 필요에 따라 레지스트리 키를 설정하여 [클라이언트 워크스테이션에 캐시되는 항목을 제어](set-defaults-for-enterprise-deployments.md)합니다.

7. 선택한 배포 기술을 사용하여 대상 개발자 워크스테이션의 이전 단계에서 생성된 스크립트를 실행합니다.

8. 1단계에서 사용한 명령을 정기적으로 실행하여 업데이트된 구성 요소를 추가하는 방법으로 [네트워크 위치를 최신 업데이트로 갱신](update-a-network-installation-of-visual-studio.md)합니다.

> [!IMPORTANT]
> 네트워크 공유에서 설치하는 경우 소스 위치가 “기억”됩니다. 이는 클라이언트 컴퓨터 복구 시 클라이언트가 원래 설치된 네트워크 공유로 돌아가야 할 수도 있음을 의미합니다. 조직에서 Visual Studio 2017 클라이언트를 실행하는 예상 수명에 맞도록 네트워크 위치를 신중하게 선택합니다.

## <a name="use-visual-studio-tools"></a>Visual Studio 도구 사용

클라이언트 컴퓨터에 [설치된 Visual Studio 인스턴스를 검색 및 관리](tools-for-managing-visual-studio-instances.md)하는 데 사용할 수 있는 여러 가지 도구가 있습니다.

> [!TIP]
> 관리자 가이드의 문서 외에도 Visual Studio 2017 설치 방법에 대한 유용한 정보 소스는 [Visual Studio Setup Archives](https://devblogs.microsoft.com/setup/tag/vs2017/)를 참조하세요.

## <a name="specify-customer-feedback-settings"></a>사용자 의견 설정 지정

기본적으로 Visual Studio 설치에서는 고객 의견을 허용합니다. 그룹 정책을 사용하면 개별 컴퓨터에서 고객 피드백을 사용하지 않도록 Visual Studio를 구성할 수 있습니다. 이렇게 하려면 다음 키에 레지스트리 기반 정책을 설정합니다.

**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\VisualStudio\SQM**

항목 = **OptIn**

값 = (DWORD)
* **0**은 옵트아웃된 것입니다.
* **1**은 옵트인된 것입니다.

고객 의견 설정에 대한 자세한 내용은 [Visual Studio 사용자 환경 개선 프로그램](../ide/visual-studio-experience-improvement-program.md) 페이지를 참조하세요.

[!INCLUDE[install_get_support_md](includes/install_get_support_md.md)]

## <a name="see-also"></a>참고 항목

* [Visual Studio 2017 설치](install-visual-studio.md)
* [명령줄 매개 변수를 사용하여 Visual Studio 2017 설치](use-command-line-parameters-to-install-visual-studio.md)
  * [명령줄 매개 변수 예](command-line-parameter-examples.md)
  * [워크로드 및 구성 요소 ID 참조](workload-and-component-ids.md)
* [Visual Studio의 네트워크 기반 설치 만들기](create-a-network-installation-of-visual-studio.md)
  * [Visual Studio 오프라인 설치에 필요한 인증서 설치](install-certificates-for-visual-studio-offline.md)
* [지시 파일을 사용하여 Visual Studio 자동화](automated-installation-with-response-file.md)
* [Visual Studio를 배포할 때 제품 키를 자동으로 적용](automatically-apply-product-keys-when-deploying-visual-studio.md)
* [Visual Studio의 엔터프라이즈 배포에 대한 기본값 설정](set-defaults-for-enterprise-deployments.md)
* [패키지 캐시를 사용하지 않도록 설정 또는 이동](disable-or-move-the-package-cache.md)
* [Visual Studio의 네트워크 기반 설치 업데이트](update-a-network-installation-of-visual-studio.md)
* [Visual Studio 배포에 대한 업데이트 제어](controlling-updates-to-visual-studio-deployments.md)
* [Visual Studio 인스턴스 검색 및 관리 도구](tools-for-managing-visual-studio-instances.md)

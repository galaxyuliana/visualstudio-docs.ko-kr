---
title: '방법: 특정 릴리스 설치 | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
helpviewer_keywords:
- install a specific release, Visual Studio
ms.assetid: d69ad0f8-f0a0-438e-a0ef-777c4868f139
caps.latest.revision: 20
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: b5f74512d0c035a82845d77f4b3df12633036f03
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54756362"
---
# <a name="how-to-install-a-specific-release-of-visual-studio"></a>방법: Visual Studio의 특정 릴리스 설치
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

선택적 기능의 최적화된 최신 버전을 사용할 수 있도록 Visual Studio 설치가 종종 업데이트됩니다.  하지만 이전 릴리스의 Visual Studio 2015(예: iOS 지원을 포함하는 Visual Studio 서전 업데이트 1 릴리스)를 설치하려면 Visual Studio 설치에서 해당 기능 매니페스트 파일의 이전 버전을 사용하도록 강제해야 합니다. 이 문서에서는 그렇게 하는 방법을 설명합니다.

## <a name="installing-the-current-release"></a>현재 릴리스 설치
 Visual Studio 2015의 초기 릴리스 이후 업데이트 했습니다 설치 엔진 및 매니페스트 파일이 여러 번.  즉,에서 웹 설치 관리자를 다운로드 하는 경우는 [Visual Studio 다운로드](https://www.visualstudio.com/downloads/download-visual-studio-vs) 깨끗 하 고 인터넷에 연결 된 컴퓨터에서 웹 사이트에 설치 된 최신 Visual Studio 2015 업데이트 제품의 최신 향상 기능을 포함 하는 선택적 기능 및 도구의 새 버전으로 최신 버전입니다.

## <a name="installing-earlier-releases"></a>이전 릴리스 설치
 만들 하 고 ISO 이미지를 탑재 하거나 다운로드 하 여에서 직접 설치 관리자를 시작할 수 있습니다 [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015) 다음 추가 명령줄 매개 변수를 사용 하 여.exe 파일을 추가 하 고 (예: /CustomInstallPath, 전체 / / InstallSelectableItems, /NoRestart 등.) Visual Studio 설치 되는 방법을 제어 합니다.

 다음 표에서 몇 가지 특정 시점에 시나리오와 Enterprise edition 설치 관리자에 전달 해야 필요한 명령줄 매개 변수를 포함 합니다. (동일한 매개 변수가 Community 또는 Professional 버전 설치 관리자에도 적용됩니다.)

|Visual Studio 2015 버전|실행할 버전|사용할 명령줄|설치 프로그램에서 수행하는 작업|
|--------------------------------|-----------------|--------------------------|---------------------|
|Visual Studio Enterprise(최신 공개 릴리스)|업데이트를 사용 하 여 visual Studio Enterprise (에서 사용 가능한 [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20enterprise%202015))|`vs_enterprise.exe` **참고:**  이 설치의 기본 동작에서는 최신 선택적 기능을 제공하므로 명령줄 매개 변수가 필요하지 않습니다.|Visual Studio 설치 프로그램에서 최신 feed.xml를 사용하고 최신 파일을 설치합니다.|
|Visual Studio Enterprise 업데이트 3(업데이트 3 세대의 추가 업데이트를 포함하지 않는 원래 업데이트 3)|Visual Studio Enterprise RTM( [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/6/B/B/6BBD3561-D764-4F39-AB8E-05356A122545/20160628.2/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 3 릴리스 때 제공 된 feed.xml를 사용 합니다.|
|Visual Studio Enterprise 업데이트 2 (원래 Update 2, 하지만 업데이트는 이전의 업데이트 3)|Visual Studio Enterprise RTM( [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/6/B/B/6BBD3561-D764-4F39-AB8E-05356A122545/20160620.2/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 3 출시 전의 최신 feed.xml를 사용합니다.|
|Visual Studio Enterprise (업데이트 2-연대 업데이트 추가 하지 않고도 원래 업데이트 2)|Visual Studio Enterprise RTM( [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/0/6/B/06BB0C5C-C767-4250-91DA-AB463377597E/20160405.3/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 2가 릴리스되면 제공 된 feed.xml를 사용 합니다.|
|Visual Studio Enterprise 업데이트 1 (원래 업데이트 1, 하지만 업데이트는 이전의 업데이트 2)|Visual Studio Enterprise RTM( [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI http://download.microsoft.com/download/3/2/A/32A1974F-D236-43C1-8981-97DDCBAEF14A/20160225.3/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 2 출시 전의 최신 feed.xml를 사용합니다.|
|Visual Studio Enterprise 업데이트 1(업데이트 1 세대의 추가 업데이트를 포함하지 않는 원래 업데이트 1)|Visual Studio Enterprise RTM( [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/3/2/A/32A1974F-D236-43C1-8981-97DDCBAEF14A/20151201.1/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 1 출시 하는 경우 제공 된 feed.xml를 사용 합니다.|
|Visual Studio Enterprise(원래 RTM이지만 업데이트 1 이전의 업데이트 포함)|Visual Studio Enterprise RTM(  [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/3/6/1/36188D5F-479F-4A46-BF55-6AE5928D1EBB/20151102.3/enu/feed.xml`|Visual Studio 설치 프로그램에서 업데이트 1 출시 전의 최신 feed.xml를 사용합니다.|
|Visual Studio Enterprise(업데이트를 포함하지 않는 원래 RTM)|Visual Studio Enterprise RTM( [MSDN 구독자 다운로드 페이지](https://msdn.microsoft.com/subscriptions/downloads/)에서 이용 가능)|`vs_enterprise.exe /OverrideFeedURI https://download.microsoft.com/download/5/7/B/57BF5016-E4F0-4EB5-BE27-2BFA87E7723F/20150713.1/enu/feed.xml`|Visual Studio 설치 프로그램에서 RTM 출시 하는 경우 사용할 수 있었던 feed.xml를 사용 합니다.|

> [!IMPORTANT]
>  사용하려는 언어에 따라 "enu"(영어)를 다음 값 중 하나로 바꾸세요.
>
> - chs(중국어 간체)
>   -   cht(중국어 번체)
>   -   csy(체코어)
>   -   deu(독일어)
>   -   esn(스페인어)
>   -   fra(프랑스어)
>   -   ita(이탈리아어)
>   -   jpa(일본어)
>   -   kor(한국어)
>   -   plk(폴란드어)
>   -   ptb(포르투갈어)
>   -   rus(러시아어)
>   -   trk(터키어)

## <a name="see-also"></a>참고 항목
 [Visual Studio 관리자 가이드](../install/visual-studio-administrator-guide.md)
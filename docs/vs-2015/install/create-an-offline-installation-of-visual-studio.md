---
title: 오프 라인 설치 만들기 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-install
ms.topic: conceptual
f1_keywords:
- offline installation
- offline install
- ISO
ms.assetid: 85d65709-42be-449f-9663-914bf1045089
caps.latest.revision: 22
author: TerryGLee
ms.author: tglee
manager: jillfra
ms.openlocfilehash: 8d76e4b1c9a7f7b6882eccab4a250e95c7419ea0
ms.sourcegitcommit: a83c60bb00bf95e6bea037f0e1b9696c64deda3c
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/19/2019
ms.locfileid: "54763135"
---
# <a name="create-an-offline-installation-of-visual-studio"></a>Visual Studio의 오프라인 설치 만들기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Visual Studio 2017에 대 한 최신 설명서를 참조 하세요 [낮은 대역폭 또는 불안정 한 네트워크 환경에 Visual Studio 2017 설치](https://docs.microsoft.com/visualstudio/install/install-vs-inconsistent-quality-network), 또는 [Visual Studio 2017의 네트워크 설치 만들기](https://docs.microsoft.com/visualstudio/install/create-a-network-installation-of-visual-studio) 및 [오프 라인 환경에서 Visual Studio 2017을 설치 하는 것에 대 한 특별 고려 사항](https://docs.microsoft.com/visualstudio/install/install-visual-studio-in-offline-environment)합니다.

이 페이지에는 인터넷에 연결 되지 않은 경우 Visual Studio 2015를 설치 하는 방법을 설명 합니다. 그러나 "연결이 끊긴된 된" 설치를 수행 하려면 먼저 만들어야 오프 라인 설치 레이아웃을 인터넷에 연결 되어 있는 컴퓨터를 사용 합니다. 방법은 다음과 같습니다.

> [!IMPORTANT]
>  오프 라인 컴퓨터 Windows 7 SP1 또는 Windows Server 2008 R2를 실행 하는 경우의 특수 한 지침을 참조 하세요 합니다 [오프 라인 설치 문제 해결](#BKMK_tshoot) 이 항목의 섹션입니다.  이러한 지침을 따라야 *하기 전에* Visual Studio 2015를 설치 합니다.

##  <a name="BKMK_Offline"></a> 오프 라인 설치를 만들어 설치

#### <a name="to-create-an-offline-installation-layout"></a>오프 라인 설치 레이아웃을 만들려면

1.  설치 하려면 Visual Studio의 버전을 선택 합니다 [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20Enterprise%202015) 페이지를 다운로드 합니다.

2.  파일 시스템에서 위치에 설치 관리자를 다운로드 한 후 실행 "\<실행 파일 이름 > /layout"입니다.

     예를 들어 다음을 실행합니다. `vs_enterprise.exe /layout D:\VisualStudio2015`

     사용 하 여는 `/layout` 스위치, 거의 모든 설치 패키지를 다운로드 컴퓨터에 적용 되는 것 뿐 아니라 다운로드할 수 있습니다. 이 방법을 사용 하면 모든 곳에서이 설치 관리자를 실행 해야 하는 파일 및 원래 설치 되지 않은 구성 요소를 설치 하려는 경우에 유용할 수 있습니다.

3.  이 명령을 실행 하면 상주할 오프 라인 설치 레이아웃을 원하는 폴더를 변경할 수 있는 대화 상자가 나타납니다.   다음을 클릭 합니다 **다운로드** 단추입니다.

     패키지 다운로드 되 면 표시 되어야 한다는 내용의 메시지가 **설치 성공!** 라고 표시된 Visual Studio 화면이 나타납니다.

4.  이전에 지정한 폴더를 찾습니다. (예를 들어 찾습니다 D:\VisualStudio2015를.) 이 폴더 공유 위치에 복사 하거나 미디어를 설치 하는 데 필요한 모든 포함 합니다.

    > [!CAUTION]
    >  현재 Android SDK에는 오프라인 설치 환경을 지원하지 않습니다. 인터넷에 연결되지 않은 컴퓨터에서 Android SDK 설치 항목을 설치하면 설치가 실패할 수 있습니다. 자세한 내용은이 항목의 "오프 라인 설치 문제 해결" 섹션을 참조 하세요.

5.  파일 위치 또는 설치 미디어에서 설치를 실행 합니다.

## <a name="updating-an-offline-installation"></a>오프 라인 설치를 업데이트 하는 중
 Microsoft Visual Studio 2015에 대 한 여러 업데이트를 출시 했습니다. Visual Studio 설치를 업데이트 하려면 단순히에서 버전을 다운로드 합니다에서 합니다 [My.VisualStudio.com](https://my.visualstudio.com/downloads?q=visual%20studio%20Enterprise%202015) 다운로드 페이지입니다. 다음 새 오프 라인 설치 레이아웃을 만들려면이 항목에 설명 된 단계에 따라 다음 Visual Studio 2015의 복사본을 업데이트 하려면 사용 합니다.

##  <a name="BKMK_tshoot"></a> 오프 라인 설치 문제 해결
 오프라인 설치 캐시에서 오프라인으로 설치하는 경우 일부 구성 요소와 패키지를 설치할 수 없다는 경고 메시지가 표시될 수도 있습니다. 다음 표에는 이러한 시나리오에 대한 가능한 해결 방법이 포함되어 있습니다.


|                                                                                       구성 요소 또는 패키지                                                                                       |                                                                                                                                                                                                                                                                                                                                                                                                   솔루션                                                                                                                                                                                                                                                                                                                                                                                                   |
|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Dotfuscator 및 Analytics Community Edition 5.19.1 (Community, Professional 및 Enterprise 버전의 Visual Studio에 설치 되어 **Windows 7 SP1** 하 고 **Windows Server 2008 R2**) |                                                                                                                                       오프 라인 컴퓨터에서 실행 중인 경우 **Windows 7 SP1** 하거나 **Windows Server 2008 R2**, Visual Studio 2015를 설치 하기 전에 다음 단계를 수행 해야 합니다.<br /><br /> 1.  CTL 파일을 다운로드 하도록 파일 또는 웹 서버를 구성 합니다.<br /><br /> 2.    연결이 끊어진된 환경에 대 한 Microsoft 자동 업데이트 URL 리디렉션.<br /><br /> 자세한 내용은 참조는 [신뢰할 수 있는 루트 구성 및 허용 되지 않는 인증서](https://technet.microsoft.com/library/dn265983.aspx) Microsoft TechNet 사이트에서 페이지.                                                                                                                                       |
|                                                                                  Android SDK 설치(API 수준)                                                                                   |                                                                        Android SDK(API 수준) 패키지를 설치하려면 인터넷 연결이 있어야 합니다. 제한된 네트워크에 있는 경우 Visual Studio를 설치할 때 다음 URL에 대한 액세스를 허용해야 합니다.<br /><br /> -   http://dl.google.com:443<br />-   http://dl-ssl.google.com:443<br />-   https://dl-ssl.google.com/android/repository/*<br /> <br />가능한 프록시 설정 문제를 해결하는 방법에 대한 자세한 내용은 [프록시를 사용하는 Visual Studio 2015 설치 오류(Android SDK 설정)](https://blogs.msdn.microsoft.com/peterhauge/2016/09/22/visual-studio-2015-install-failures-android-sdk-setup-behind-a-proxy/) 블로그 게시물을 참조하세요.                                                                         |
|                             Visual Studio 확장성 항목 템플릿<br /><br /> Visual Studio용 GitHub 확장<br /><br /> PowerShell Tools for Visual Studio                             | Visual Studio 2015를 설치할 때 인터넷에 연결 되지 않은, 경우에 특별 한 오프 라인 설치 레이아웃을 생성 하려면 오프 라인 피드를 사용할 수 있습니다. **참고:** 이 특별 한 피드 Visual Studio 2015에 최신 업데이트가 포함 됩니다. <br /><br /> 특수 한 오프 라인 피드를 만들려면 다음 명령을 실행: /layout *Drive:* \VisualStudio2015 /overridefeeduri *xml 피드 URL*<br /><br /> 예를 들어 영어 언어에 대 한 특별 한 오프 라인 피드의 Visual Studio 2015 Enterprise를 실행 합니다.<br /><br /> `vs_enterprise_ENU.exe /layout D:\VisualStudio2015 /overridefeeduri "http://go.microsoft.com/fwlink/?LinkID=785882&clcid0x409"`<br /><br /> 사용자가 선택한 언어는 특수 한 오프 라인 피드를 만드는 데 사용할 수 있는 Url 목록을 완료에 대 한 아래 표를 참조 합니다. |

 위의 표에 설명 된 대로 언어별 특별 한 오프 라인 피드를 만들려면 다음 Url을 사용 합니다.


|       언어        |                            URL                            |
|-----------------------|-----------------------------------------------------------|
| 및  | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x804 |
| 옵션 대신, | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x404 |
|         체코어         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x405 |
|        독일어         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x407 |
|        영어        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x409 |
|        스페인어        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0xC0A |
|        프랑스어         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x40C |
|        이탈리아어        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x410 |
|       일본어        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x411 |
|        한국어         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x412 |
|        폴란드어         | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x415 |
|      포르투갈어       | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x416 |
|        러시아어        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x419 |
|        터키어        | http://go.microsoft.com/fwlink/?LinkID=785882&clcid=0x41F |

## <a name="see-also"></a>참고 항목
 [Visual Studio 설치]()
---
title: 프로젝트 디자이너, 게시 페이지 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- Microsoft.VisualStudio.Publish.ClickOnceProvider.Dialog.PropertyPage
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- Project Designer, Publish page
- Publish page in Project Designer
ms.assetid: 153527c6-8b95-4003-8e8e-03a489d0a629
caps.latest.revision: 37
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f135221564583d2d9726bb9fa153840b1328e96f
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65701822"
---
# <a name="publish-page-project-designer"></a>프로젝트 디자이너, 게시 페이지
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**프로젝트 디자이너** 의 **게시** 페이지를 통해 ClickOnce 배포를 위한 속성을 구성합니다.  
  
 이 **게시** 페이지에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 **프로젝트** 메뉴에서 **속성**을 클릭합니다. **프로젝트 디자이너** 가 나타나면 **게시** 탭을 클릭합니다.  
  
> [!NOTE]
> 여기에 설명된 ClickOnce 속성 중 일부는 **빌드** 메뉴에서 또는 이 페이지의 **PublishWizard** 단추를 클릭하여 사용할 수 있는 **PublishWizard**에서도 설정할 수 있습니다.  
  
## <a name="uielement-list"></a>UI 요소 목록  
 **게시 폴더 위치**  
 애플리케이션이 게시되는 위치를 지정합니다. 드라이브 경로(`C:\deploy\myapplication`), 파일 공유(`\\server\myapplication`), FTP 서버(`ftp://ftp.microsoft.com/myapplication`) 또는 웹 사이트(`http://www.microsoft.com/myapplication`)일 수 있습니다. 찾아보기( **...** ) 단추가 작동하려면**게시 위치**상자에 텍스트가 있어야 합니다.  
  
 기본적으로 게시 위치는 IIS를 설치한 경우 `http://localhost/<projectname>/` , 또는 IIS를 설치하지 않은 경우 `publish\` 디렉터리입니다. 컴퓨터에서 Windows Vista가 실행 중인 경우 IIS의 설치 여부와 상관없이 기본값은 항상 `publish\` 디렉터리입니다.  
  
 **설치 폴더 URL**  
 선택 사항입니다. 사용자가 애플리케이션을 설치할 웹 사이트를 지정합니다. **게시 위치**와 다른 경우(예: 응용 프로그램이 준비 서버에 게시된 경우)에만 이 옵션이 필요합니다.  
  
 **설치 모드 및 설정**  
 애플리케이션을 **게시 위치** 에서 직접 실행할지( **온라인으로만 애플리케이션 사용 가능** 선택 시), 또는 설치하여 **시작** 메뉴 및 **제어판** 의 **프로그램 추가/제거** 항목에 추가할지( **오프라인으로도 애플리케이션 사용 가능** 선택 시)를 결정합니다.  
  
 WPF 웹 브라우저 애플리케이션의 경우 온라인으로만 사용 가능하므로, **오프라인으로도 애플리케이션 사용 가능** 옵션을 사용할 수 없습니다.  
  
 **응용 프로그램 파일**  
 개별 파일을 어디에 어떻게 설치할지를 지정하는 데 사용되는 [Application Files Dialog Box](https://msdn.microsoft.com/b06dff3a-b87a-4caf-996b-7a4acf8137a8)를 엽니다.  
  
 **필수 구성 요소**  
 .NET Framework 같은 필수 구성 요소를 애플리케이션과 함께 설치하도록 지정하는 데 사용되는 [Prerequisites Dialog Box](../../ide/reference/prerequisites-dialog-box.md)를 엽니다.  
  
 **Updates**  
 애플리케이션의 업데이트 동작을 지정하는 데 사용되는 [Application Updates Dialog Box](https://msdn.microsoft.com/8eca8743-8e68-4d04-bfd5-4dc0a9b2934f)를 엽니다. **온라인으로만 응용 프로그램 사용 가능** 을 선택한 경우 사용할 수 없습니다.  
  
 **옵션**  
 추가 고급 게시 옵션을 지정하는 데 사용되는 [Publish Options Dialog Box](https://msdn.microsoft.com/fd9baa1b-7311-4f9e-8ffb-ae50cf110592)를 엽니다.  
  
 **게시 버전**  
 애플리케이션의 게시 버전 번호를 설정합니다. 버전 번호가 변경되면 애플리케이션이 업데이트로 게시됩니다. 게시 버전의 각 부분(**주**, **부**, **빌드**, **수정**)에 사용할 수 있는 최대 값은 65355입니다(<xref:System.UInt16.MaxValue>). 이는 <xref:System.Version>에서 허용하는 최대 값입니다.  
  
 ClickOnce를 사용하여 애플리케이션 버전을 둘 이상 설치하면 이전 애플리케이션 버전이 지정한 게시 위치의 Archive 폴더로 이동합니다. 이러한 방식으로 이전 버전이 보관되므로 설치 디렉터리에 이전 버전의 폴더가 남지 않습니다.  
  
 **게시할 때마다 자동으로 수정 번호 증가**  
 선택 사항입니다. 이 옵션이 선택된 경우(기본값), 애플리케이션을 게시할 때마다 게시 버전 번호의 **수정** 부분이 1씩 증가합니다. 그러면 애플리케이션이 업데이트로 게시됩니다.  
  
 **게시 마법사**  
 [Publish Wizard](https://msdn.microsoft.com/fc6abebd-13d6-48e4-a567-fbc52dad0872)를 엽니다. 게시 마법사를 완료하는 것은 **빌드** 메뉴의 **게시** 명령을 실행하는 것과 효과가 동일합니다.  
  
 **지금 게시**  
 현재 설정을 사용하여 애플리케이션을 게시합니다. **PublishWizard**에서 **마침** 단추와 동일합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 응용 프로그램 게시](../../deployment/publishing-clickonce-applications.md)   
 [방법: 게시 마법사를 사용 하 여 ClickOnce 응용 프로그램 게시](../../deployment/how-to-publish-a-clickonce-application-using-the-publish-wizard.md)   
 [방법: Visual Studio에서 파일을 복사 하는 위치 지정](../../deployment/how-to-specify-where-visual-studio-copies-the-files.md)   
 [방법: 최종 사용자를 설치할 위치를 지정 합니다.](../../deployment/how-to-specify-the-location-where-end-users-will-install-from.md)   
 [방법: 기술 지원에 대 한 링크를 지정 합니다.](../../deployment/how-to-specify-a-link-for-technical-support.md)   
 [방법: 지정 ClickOnce 오프 라인 또는 온라인 설치 모드](../../deployment/how-to-specify-the-clickonce-offline-or-online-install-mode.md)   
 [방법: CD 설치를 위한 자동 시작 사용](../../deployment/how-to-enable-autostart-for-cd-installations.md)   
 [방법: 게시 버전 설정 ClickOnce](../../deployment/how-to-set-the-clickonce-publish-version.md)   
 [방법: 게시 버전 자동 증가 ClickOnce](../../deployment/how-to-automatically-increment-the-clickonce-publish-version.md)   
 [방법: ClickOnce를 통해 게시할 파일 지정](../../deployment/how-to-specify-which-files-are-published-by-clickonce.md)   
 [방법: ClickOnce 응용 프로그램을 사용 하 여 필수 구성 요소 설치](../../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램에 대 한 업데이트 관리](../../deployment/how-to-manage-updates-for-a-clickonce-application.md)   
 [방법: 변경 된 ClickOnce 응용 프로그램에 대 한 게시 언어](../../deployment/how-to-change-the-publish-language-for-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램에 대 한 시작 메뉴 이름 지정](../../deployment/how-to-specify-a-start-menu-name-for-a-clickonce-application.md)   
 [방법: ClickOnce 응용 프로그램의 게시 페이지 지정](../../deployment/how-to-specify-a-publish-page-for-a-clickonce-application.md)   
 [ClickOnce 보안 및 배포](../../deployment/clickonce-security-and-deployment.md)

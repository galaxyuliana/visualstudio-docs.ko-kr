---
title: '방법: ClickOnce 응용 프로그램을 사용 하 여 필수 구성 요소를 포함 합니다. | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c66bf0a5-8c93-4e68-a224-3b29ac36fe4d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 47142e63976a743166e5211631e77a0c0878ad9c
ms.sourcegitcommit: 47eeeeadd84c879636e9d48747b615de69384356
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "63406961"
---
# <a name="how-to-include-prerequisites-with-a-clickonce-application"></a>방법: ClickOnce 애플리케이션의 필수 구성 요소 포함
[!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 애플리케이션에 필요한 구성 요소 소프트웨어를 배포하기 전에 먼저 이러한 필수 구성 요소용 설치 관리자 패키지를 개발 컴퓨터로 다운로드해야 합니다. 애플리케이션을 게시하고 **내 애플리케이션과 동일한 위치에서 필수 구성 요소 다운로드**를 선택할 경우, 설치 관리자 패키지가 **패키지** 폴더에 있지 않으면 오류가 발생합니다.

> [!NOTE]
> .NET Framework 용 설치 관리자 패키지를 추가 하려면 참조 [개발자를 위한.NET Framework 배포 가이드](/dotnet/framework/deployment/deployment-guide-for-developers)합니다.

## <a name="Package"></a> Package.xml을 사용하여 설치 관리자 패키지를 추가하려면

1. 파일 탐색기에서 **패키지** 폴더를 엽니다.

    기본적으로 경로 `%ProgramFiles(x86)%\Microsoft SDKs\ClickOnce Bootstrapper\Packages\`합니다.

2. 추가하려는 필수 구성 요소에 대한 폴더를 연 다음, 설치된 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 버전의 언어 폴더를 엽니다(예: 영어는 **en**).

3. 메모장에서 *Package.xml* 파일을 엽니다.

4. 찾을 합니다 **이름을** 포함 하는 요소 **http://go.microsoft.com/fwlink** , URL을 복사 합니다. **LinkID** 부분을 포함합니다.

   > [!NOTE]
   > 없으면 **이름** 요소에 포함 되어 **http://go.microsoft.com/fwlink** 엽니다는 **Product.xml** 필수 구성 요소에 대 한 루트 폴더에 파일을 찾습니다는 **fwlink** 문자열입니다.

   > [!IMPORTANT]
   > 일부 필수 구성 요소에는 여러 개의 설치 관리자 패키지가 있습니다(예: 32비트 또는 64비트 시스템). 여러 **이름** 요소에 **fwlink**가 있을 경우 각각에 대해 나머지 단계를 반복해야 합니다.

5. 브라우저의 주소 표시줄에 URL을 붙인 다음, 실행 또는 저장하라는 메시지가 표시되면 **저장**을 선택합니다.

    이 단계에서는 설치 관리자 파일을 컴퓨터에 다운로드합니다.

6. 필수 구성 요소의 루트 폴더에 파일을 복사합니다.

    예를 들어 Windows Installer 4.5 필수 구성 요소의 경우 파일을 *\Packages\WindowsInstaller4_5* 폴더에 복사합니다.

    이제 애플리케이션으로 설치 관리자 패키지를 배포할 수 있습니다.

## <a name="see-also"></a>참고자료
- [방법: ClickOnce 응용 프로그램을 사용 하 여 필수 조건 설치](../deployment/how-to-install-prerequisites-with-a-clickonce-application.md)

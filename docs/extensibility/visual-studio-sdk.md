---
title: Visual Studio SDK | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- VSSDK.v90.StartPage
helpviewer_keywords:
- Visual Studio SDK
- VS SDK (see Visual Studio SDK)
- Visual Studio, SDK
ms.assetid: 1f7c348a-114c-4243-b392-3531e9c9c6fd
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: be0d7246af3b43d76ee4531a426dab0af63e2aff
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56711724"
---
# <a name="visual-studio-sdk"></a>Visual Studio SDK
Visual Studio SDK를 사용 하면 Visual Studio 기능을 확장 하거나 Visual Studio에 새 기능을 통합할 수 있습니다. Visual Studio Marketplace 뿐만 아니라 다른 사용자에 게 확장을 배포할 수 있습니다. 다음은 Visual Studio를 확장할 수 있는 몇 가지 방법입니다.

- IDE에 명령, 단추, 메뉴 및 기타 UI 요소 추가

- 새로운 기능에 대 한 도구 창 추가

- 지정된 된 언어에 대 한 IntelliSense를 확장 하거나 새 프로그래밍 언어에 대 한 IntelliSense를 제공 합니다.

- 전구를 사용 하 여 더 나은 코드를 작성할 힌트와 개발자는 데 도움이 되는 제안 제공

- 새 언어에 대 한 지원을 사용 하도록 설정

- 사용자 지정 프로젝트 형식을 추가합니다

- 수백만 명의 개발자가 Visual Studio Marketplace를 통해 도달

  및 이러한 기능에 대 한 자세한 내용은 하기 전에 Visual Studio 확장을 써 본 적, 경우 찾아야 [Visual Studio 확장 개발 시작](../extensibility/starting-to-develop-visual-studio-extensions.md)합니다.

## <a name="install-the-visual-studio-sdk"></a>Visual Studio SDK 설치
 Visual Studio SDK는 Visual Studio 설치에서 선택적 기능입니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.

## <a name="whats-new-in-the-visual-studio-2017-sdk"></a>Visual Studio 2017 SDK의 새로운 기능
 Visual Studio SDK의 주요 변경 내용에 확장을 업데이트 해야 할 수도 있습니다는 뿐만 아니라 VSIX v3 형식 같은 몇 가지 새로운 기능에 있습니다. 자세한 내용은 [Visual Studio 2017 SDK의 새로운 기능](../extensibility/what-s-new-in-the-visual-studio-2017-sdk.md)합니다.

## <a name="visual-studio-user-experience-guidelines"></a>Visual Studio 사용자 환경 지침
 확장에 대 한 UI를 디자인 하기 위한 유용한 팁을 얻을 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.

 높은 DPI 장치에서 훌륭해 확장 하는 방법을 알아볼 수 있습니다 합니다 [주소 DPI 문제](../extensibility/addressing-dpi-issues2.md) 문서.

 활용 합니다 [이미지 서비스 및 카탈로그](../extensibility/image-service-and-catalog.md) 유용한 이미지 관리 및 높은 DPI 및 테마에 대 한 지원.

## <a name="find-and-install-existing-visual-studio-extensions"></a>기존 Visual Studio 확장명 찾기 및 설치
 Visual Studio 확장을 찾을 수 있습니다 합니다 **확장 및 업데이트** 대화 상자를 **도구** 메뉴. 자세한 내용은 [찾기 및 사용 하 여 Visual Studio 확장](../ide/finding-and-using-visual-studio-extensions.md)합니다. 확장을 찾을 수도 있습니다는 [Visual Studio marketplace](https://marketplace.visualstudio.com/)

## <a name="visual-studio-sdk-reference"></a>Visual Studio SDK 참조
 Visual Studio SDK API 참조를 찾을 수 있습니다 [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)합니다.

## <a name="visual-studio-sdk-samples"></a>Visual Studio SDK 샘플
 GitHub의에서 VS SDK 확장의 오픈 소스 예제를 찾을 수 있습니다 [Visual Studio 샘플](https://aka.ms/vs2015sdksamples)합니다. 이 GitHub 리포지토리는 Visual Studio의 확장 가능한 다양 한 기능을 보여 주는 샘플이 포함 되어 있습니다.

## <a name="other-visual-studio-sdk-resources"></a>다른 Visual Studio SDK 리소스
 VSSDK에 대 한 질문 했거나 확장 개발 경험을 공유 하려는 경우 사용할 수 있습니다 합니다 [Visual Studio 확장성 포럼](https://social.msdn.microsoft.com/Forums/vstudio/home?forum=vsx) 또는 [ExtendVS Gitter Chatroom](https://gitter.im/Microsoft/extendvs)합니다.

 자세한 내용을 볼 수는 [VSX 실수가 블로그](https://blogs.msdn.microsoft.com/vsx/) 및 다양 한 Microsoft Mvp가 작성 한 블로그:

-   [즐겨 사용 하는 Visual Studio 확장](http://geekswithblogs.net/sdorman/archive/2014/10/05/favorite-visual-studio-extensions.aspx)

-   [Visual Studio 확장성](http://www.visualstudioextensibility.com/overview/vs/)

-   [Visual Studio 확장](http://blog.slaks.net/2013-10-18/extending-visual-studio-part-1-getting-started/)

## <a name="see-also"></a>참고자료
- [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)
- [방법: Visual Studio 2017로 확장성 프로젝트 마이그레이션](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2017.md)
- [자주 묻는 질문(FAQ): 추가 기능을 VSPackage 확장으로 변환](../extensibility/faq-converting-add-ins-to-vspackage-extensions.md)
- [관리 코드에서 다중 스레드 관리](../extensibility/managing-multiple-threads-in-managed-code.md)
- [메뉴 및 명령 확장](../extensibility/extending-menus-and-commands.md)
- [도구 모음에 명령 추가](../extensibility/adding-commands-to-toolbars.md)
- [확장 및 사용자 지정 도구 창](../extensibility/extending-and-customizing-tool-windows.md)
- [편집기 및 언어 서비스 확장](../extensibility/editor-and-language-service-extensions.md)
- [프로젝트를 확장 합니다.](../extensibility/extending-projects.md)
- [사용자 설정 및 옵션 확장](../extensibility/extending-user-settings-and-options.md)
- [사용자 지정 프로젝트 및 항목 템플릿 만들기](../extensibility/creating-custom-project-and-item-templates.md)
- [속성 및 속성 창 확장](../extensibility/extending-properties-and-the-property-window.md)
- [Visual Studio의 다른 부분 확장](../extensibility/extending-other-parts-of-visual-studio.md)
- [서비스 제공 및 사용](../extensibility/using-and-providing-services.md)
- [Vspackage 관리](../extensibility/managing-vspackages.md)
- [Visual Studio 격리 셸](/visualstudio/extensibility/shell/visual-studio-isolated-shell)
- [Visual Studio 확장 기능 제공](../extensibility/shipping-visual-studio-extensions.md)
- [Visual Studio SDK 기본 사항](../extensibility/internals/inside-the-visual-studio-sdk.md)
- [Visual Studio SDK 지원](../extensibility/support-for-the-visual-studio-sdk.md)
- [보관](../extensibility/archive.md)
- [Visual Studio SDK 참조](../extensibility/visual-studio-sdk-reference.md)

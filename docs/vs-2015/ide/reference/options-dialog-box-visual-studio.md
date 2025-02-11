---
title: 옵션 대화 상자 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- vs.toolsoptionspages
helpviewer_keywords:
- Tools Options settings
- Options dialog box
- Options dialog box, development environment
- tools [Visual Studio], customizing
ms.assetid: 02b09877-1df1-4531-a0d1-a4ca17c7f857
caps.latest.revision: 23
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: bc659641e64bde9da4f1e05abf285fbdec1877e3
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65674850"
---
# <a name="options-dialog-box-visual-studio"></a>옵션 대화 상자(Visual Studio)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**옵션** 대화 상자에서는 필요에 맞게 IDE(통합 개발 환경)를 구성할 수 있습니다. 예를 들어 프로젝트의 기본 저장 위치를 설정하고, 창의 기본 모양과 동작을 변경하고, 일반적으로 사용되는 명령의 바로 가기를 만들 수 있습니다. 개발 언어 및 플랫폼에 관련된 옵션도 있습니다. **도구** 메뉴에서 **옵션**에 액세스할 수 있습니다.

> [!NOTE]
> 대화 상자에서 사용할 수 있는 옵션과 메뉴 명령의 이름 및 위치는 실제 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.

## <a name="layout-of-the-options-dialog-box"></a>옵션 대화 상자의 레이아웃
 **옵션** 대화 상자는 왼쪽 탐색 창 및 오른쪽 표시 영역의 두 부분으로 구분됩니다. 탐색 창의 트리 컨트롤에는 환경, 텍스트 편집기, 프로젝트 및 솔루션, 소스 제어와 같은 폴더 노드가 포함됩니다. 폴더 노드를 확장하여 포함된 옵션 페이지를 나열합니다. 특정 페이지에 대한 노드를 선택하면 해당 옵션이 표시 영역에 나타납니다.

 IDE 기능이 메모리에 로드될 때까지 해당 기능에 대한 옵션이 탐색 창에 나타나지 않습니다. 따라서 마지막 세션을 종료했을 때 표시된 것과 동일한 옵션이 새 세션을 시작할 때 표시되지 않을 수 있습니다. 프로젝트를 만들거나 특정 애플리케이션을 사용하는 명령을 실행하면 관련 옵션에 대한 노드가 [옵션] 대화 상자에 추가됩니다. 이러한 추가된 옵션은 IDE 기능이 메모리에 남아 있는 한 계속 사용할 수 있습니다.

> [!NOTE]
> 일부 설정 컬렉션은 [옵션] 대화 상자의 탐색 창에 나타나는 페이지의 범위를 지정합니다. **모든 설정 표시**를 선택하여 모든 가능한 페이지를 볼 수 있습니다.

## <a name="how-options-are-applied"></a>옵션 적용 방법
 **옵션** 대화 상자에서 [확인]을 클릭하면 모든 페이지의 모든 설정이 저장됩니다. 모든 페이지에서 [취소]를 클릭하면 다른 **옵션** 페이지에서 방금 변경한 내용을 포함하여 모든 변경 요청이 취소됩니다. [옵션 대화 상자, 환경, 글꼴 및 색](../../ide/reference/fonts-and-colors-environment-options-dialog-box.md)에서 변경한 내용과 같은 옵션 설정에 대한 일부 변경 내용은 Visual Studio를 닫았다 다시 열어야 적용됩니다.

### <a name="show-all-settings"></a>모든 설정 표시
 **모든 설정 표시**를 선택하거나 선택 취소하면 **확인**을 클릭하지 않았더라도 **옵션** 대화 상자에서 적용한 모든 변경 내용이 적용됩니다.

## <a name="see-also"></a>참고 항목
 [편집기 사용자 지정](../../ide/customizing-the-editor.md)

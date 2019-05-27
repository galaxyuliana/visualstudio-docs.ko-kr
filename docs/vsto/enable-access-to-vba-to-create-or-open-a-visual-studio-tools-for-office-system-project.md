---
title: VBA VSTO system 프로젝트를 만들기/열기에 대 한 액세스
decsprition: You must explicitly enable access to the Office VBA project system before you can create or open a Visual Studio Tools for Office system project
titleSuffix: Visual Studio Tools for Microsoft Office
ms.custom: seodec18
ms.date: 02/02/2017
ms.topic: conceptual
f1_keywords:
- vst.project.vbawrongversion
- VST.Project.VBASecurityGenericError
- VST.Project.VBASecurityPermissions
- VST.SelectDocWizard.MissingCOM
- VST.Project.VBASecurityNotSet
dev_langs:
- VB
- CSharp
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: c85a907b057118c28ea35b8a920337ecdad5ad01
ms.sourcegitcommit: 13ab9a5ab039b070b9cd9251d0b83dd216477203
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2019
ms.locfileid: "66177659"
---
# <a name="enable-access-to-vba-to-create-or-open-a-visual-studio-tools-for-the-microsoft-office-system-project"></a>만들거나 Visual Studio Tools for the Microsoft Office system 프로젝트를 열고는 VBA에 대 한 액세스를 사용 하도록 설정

만들거나 Visual Studio Tools for the Microsoft Office system 프로젝트를 열 수에 명시적으로 Microsoft office에서 VBA 프로젝트 시스템에 대 한 Visual Basic에 대 한 액세스를 활성화 해야 합니다.

 Microsoft Office 개발 프로젝트는 프로젝트가 응용 프로그램에 대 한 Visual Basic을 사용 하지 않는 경우에 Microsoft Office Word 및 Microsoft Office Excel에서 VBA 프로젝트 시스템에 대 한 Visual Basic에 대 한 액세스를 해야 합니다. Visual Basic 및 C# 프로젝트의 디자인 타임 컨트롤 지원은 Visual Basic for Applications 프로젝트 시스템에 따라 달라집니다.

 일부 Microsoft Office 매크로 바이러스는 자신을 전파하기 위한 수단으로 Visual Basic for Applications 프로젝트 시스템을 자동화하려 할 수 있습니다. Visual Basic for Applications 프로젝트 시스템에 액세스할 수 있도록 설정하는 순간 매크로 바이러스 확산을 방지할 수 있는 안전 기능이 작동하지 않게 되는 것입니다. 그러나 일반적인 매크로 보안은 계속 적용되므로 Office 응용 프로그램에 대해 유지 관리하는 신뢰할 수 있는 게시자 목록과 매크로 보안 수준을 통해 매크로를 컴퓨터에서 실행해도 되는지 여부가 결정됩니다.

> [!NOTE]
> 이 옵션은 개발 컴퓨터에만 적용됩니다. 최종 사용자 컴퓨터에 Office 솔루션을 실행 하도록이 옵션이 필요 하지 않습니다.

 Visual Basic for Applications 프로젝트 시스템에 액세스할 수 없도록 설정하는 것 자체만으로는 바이러스로부터 컴퓨터를 보호할 수 없으며, 컴퓨터가 매크로 바이러스에 감염되는 경우 일부 바이러스가 다른 문서로 확산되는 것을 중지할 수 있을 뿐입니다. 이 옵션은 컴퓨터에 대한 추가 보호 계층으로 기본적으로 사용하지 않도록 설정됩니다. 그러나 이 옵션을 사용하도록 설정해도 보안 모범 사례를 따르면 컴퓨터가 바이러스에 더 감염되기 쉬운 상태가 되지는 않습니다.

 보안 패치 및 바이러스 스캐너를 사용 하 여 최신 상태로 유지 하 고 Office 매크로 바이러스를 높음 또는 매우 높음 보안 수준에서 매크로만 신뢰 하에서 Office를 실행 하려면 확인 알려진된 원본에 대 한 최상의 보호 합니다.

 옵션을 사용 하지 않도록 설정 하거나 설정할 수 있습니다 **Visual Basic 프로젝트에 안전 하 게 액세스할** 수동으로.

 VBA 또는 COM 오류가 발생하는 경우에는 Office 설치를 복구할 수 있습니다.

## <a name="to-enable-or-disable-access-to-visual-basic-projects"></a>사용 하도록 설정 하거나 Visual Basic 프로젝트에 대 한 액세스를 사용 하지 않도록 설정

1. **파일** 탭을 클릭합니다.

2. **옵션**을 클릭합니다.

3. 클릭 **Trust Center**를 클릭 하 고 **보안 센터 설정**합니다.

4. 에 **보안 센터**, 클릭 **매크로 설정이**합니다.

5. 선택 또는 선택 취소 **VBA 프로젝트 개체 모델에 대 한 액세스를 신뢰** 사용 하도록 설정 하거나 Visual Basic 프로젝트에 대 한 액세스를 사용 하지 않도록 설정 합니다.

6. **확인**을 클릭합니다.

### <a name="to-enable-or-disable-access-to-visual-basic-projects-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office system 사용 하 여 Visual Basic 프로젝트에 대 한 액세스를 사용할지 설정 합니다.

1. 에 **도구** 메뉴 Word 나 Excel에서 가리킨 **매크로**를 클릭 하 고 **보안**.

2. 에 **보안** 대화 상자에서 클릭 합니다 **신뢰할 수 있는 게시자** 탭 합니다.

3. 를 사용 하도록 설정 또는 해제 하 여 비활성화를 선택할 **Visual Basic 프로젝트에 안전 하 게 액세스할**합니다.

4. **확인**을 클릭합니다.

## <a name="to-set-your-office-macro-security-level"></a>Office 매크로 보안 수준을 설정하려면

1. **파일** 탭을 클릭합니다.

2. **옵션**을 클릭합니다.

3. 클릭 **Trust Center**를 클릭 하 고 **보안 센터 설정**합니다.

4. 에 **보안 센터**, 클릭 **매크로 설정이**합니다.

5. 에 **매크로 설정이** 섹션에서 원하는 설정을 선택 합니다.

6. **확인**을 클릭합니다.

### <a name="to-set-your-office-macro-security-level-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office system 사용 하 여 Office 매크로 보안 수준을 설정 하려면

1. 에 **도구** 메뉴 Word 나 Excel에서 가리킨 **매크로**를 클릭 하 고 **보안**.

2. 에 **보안 수준** 탭에서 원하는 설정을 선택 합니다.

    합니다 **보안 수준** 탭에는 각 수준에 대 한 정보가 포함 됩니다. 자세한 내용은 Office 도움말에서 "매크로 보안 수준" 항목을 참조하세요.

### <a name="to-install-vba-with-the-2007-microsoft-office-system"></a>2007 Microsoft Office system과 함께 VBA를 설치하려면

1. 제어판에서 실행할 **프로그램 추가 / 제거** 하거나 **프로그램 및 기능**합니다.

2. Office를 선택 합니다 **현재 설치 된 프로그램** 목록입니다.

3. **변경**을 클릭합니다.

4. 선택 **기능 추가 / 제거**를 클릭 하 고 **계속**합니다.

5. 선택 **응용 프로그램의 고급 사용자 지정 선택**를 클릭 하 고 **다음**합니다.

6. 확장 **Office 공유 기능** 에 **응용 프로그램 및 도구에 대 한 업데이트 옵션을 선택** 목록입니다.

7. 옆에 드롭다운 메뉴를 연 **응용 프로그램에 대 한 Visual Basic**를 클릭 하 고 **내 컴퓨터에서 실행**합니다.

8. **Continue(계속)** 를 클릭합니다.

9. **닫기**를 클릭합니다.

## <a name="to-repair-your-installation-of-office"></a>Office 설치를 복구하려면

1. 제어판에서 실행할 **프로그램 추가 / 제거** 하거나 **프로그램 및 기능**합니다.

2. Office의 버전을 선택 합니다 **현재 설치 된 프로그램** 목록입니다.

3. **변경**을 클릭합니다.

4. 선택 **다시 설치 또는 복구**를 클릭 하 고 **다음**합니다.

5. 선택 **Office 설치에서 오류 감지 및 복구**를 클릭 하 고 **설치**합니다.

## <a name="see-also"></a>참고자료
- [Office 솔루션 보안](../vsto/securing-office-solutions.md)

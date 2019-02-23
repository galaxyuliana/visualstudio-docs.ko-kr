---
title: Visual Studio에서 템플릿 검색 문제 해결 | Microsoft Docs
ms.date: 01/02/2018
ms.topic: conceptual
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1e84ff96381fb29a1728ad43df4ff558abd17243
ms.sourcegitcommit: b0d8e61745f67bd1f7ecf7fe080a0fe73ac6a181
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/22/2019
ms.locfileid: "56689840"
---
# <a name="troubleshooting-template-installation"></a>문제 해결 템플릿 설치

프로젝트 또는 항목 템플릿을 배포 하는 문제에 봉착 한 경우에 진단 로깅을 활성화할 수 있습니다.

1. 다음 내용으로 (예: C:\Program Files (x86) \Microsoft Visual Studio\2017\Enterprise\Common7\IDE\CommonExtensions\EnablePkgDefLogging.pkgdef) 설치용 Common7\IDE\CommonExtensions 폴더에 pkgdef 파일을 만듭니다.

    ```
    [$RootKey$\VsTemplate]
    "EnableTemplateDiscoveryLog"=dword:00000001
    ```

1. 설치를 위한 Windows search에서 검색 하 여 "개발자 명령 프롬프트"를 열고 실행 `devenv /updateConfiguration`합니다.

1. Visual Studio를 시작 하 고 새 프로젝트를 새 항목 대화 상자 템플릿 양쪽 트리에 모두 초기화를 시작 합니다. 서식 파일 로그에 나타납니다 **%LOCALAPPDATA%\Microsoft\VisualStudio\15.0_[instanceid]\VsTemplateDiagnosticsList.csv** (instanceid는 Visual Studio 인스턴스의 설치 ID에 해당). 이 로그에 항목을 추가 하는 각 템플릿 트리 초기화 합니다.

로그 파일에는 다음 열을 포함 합니다.

- **FullPathToTemplate**에 다음 값입니다.

    - 매니페스트 기반 배포에 대 한 1

    - 디스크 기반 배포에 대 한 0

- **TemplateFileName**

- 다른 템플릿 속성

> [!NOTE]
> 로깅을 사용 하지 않으려면, pkgdef 파일을 제거 또는 값을 변경 `EnableTemplateDiscoveryLog` 하 `dword:00000000`, 다음 실행 `devenv /updateConfiguration` 다시 합니다.

## <a name="see-also"></a>참고자료

- [사용자 지정 프로젝트 및 항목 템플릿 만들기](creating-custom-project-and-item-templates.md)
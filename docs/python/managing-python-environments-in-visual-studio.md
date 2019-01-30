---
title: Python 환경 및 인터프리터 관리
description: Python 환경 창을 사용하여 전역, 가상 및 conda 환경을 관리하고 Python 인터프리터 및 패키지를 설치하며 Visual Studio 프로젝트에 환경을 할당합니다.
ms.date: 12/07/2018
ms.prod: visual-studio-dev15
ms.topic: conceptual
author: kraigb
ms.author: kraigb
manager: jillfra
ms.workload:
- python
- data-science
ms.openlocfilehash: e883cb199ca2959015dac0c6492d19e7875c5ca1
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54958786"
---
# <a name="how-to-create-and-manage-python-environments-in-visual-studio"></a>Visual Studio에서 Python 환경을 만들고 관리하는 방법

Python ‘환경’은 Python 코드를 실행할 컨텍스트이며 전역, 가상 및 conda 환경을 포함합니다. 환경은 인터프리터, 라이브러리(일반적으로 Python 표준 라이브러리) 및 설치된 패키지 집합으로 구성됩니다. 이러한 모든 구성 요소에 따라, 어떤 언어로 구성되고 구문이 유효한지, 어떤 운영 체제 기능에 액세스할 수 있으며 어떤 패키지를 사용할 수 있는지가 결정됩니다.

Windows의 Visual Studio에서는 이 문서에 설명된 대로 **Python 환경** 창을 사용하여 여러 환경을 관리하고 새 프로젝트의 기본값으로 하나의 환경을 선택합니다. 환경의 기타 측면은 다음 문서를 참조하십시오.

- 지정된 프로젝트의 경우 기본값을 사용하는 대신 [특정 환경을 선택](selecting-a-python-environment-for-a-project.md)할 수 있습니다.

- Python 프로젝트용 가상 환경을 만들고 사용하는 방법에 대한 자세한 내용은 [가상 환경 사용](selecting-a-python-environment-for-a-project.md#use-virtual-environments)을 참조하세요.

- 환경에 패키지를 설치하려는 경우 [패키지 탭 참조](python-environments-window-tab-reference.md#packages-tab)를 참조합니다.

- 다른 Python 인터프리터를 설치하려면 [Python 인터프리터 설치](installing-python-interpreters.md)를 참조하세요. 일반적으로 기본 Python 배포를 위해 설치 관리자를 다운로드하고 실행하는 경우 Visual Studio는 새로 설치 및 환경이 **Python 환경** 창에 표시되고 프로젝트에 대해 선택될 수 있음을 검색합니다.

Visual Studio에서 Python을 처음 사용하는 경우 다음 문서는 일반 배경에서도 제공됩니다.

- [Visual Studio에서 Python 작업](overview-of-python-tools-for-visual-studio.md)
- [Visual Studio에서 Python 지원 설치](installing-python-support-in-visual-studio.md)

> [!Note]
> 또한 **파일** > **열기** > **폴더** 명령을 사용하여 폴더로만 열리는 Python 코드의 환경을 관리할 수 없습니다. 대신 Visual Studio의 환경 기능을 사용하기 위해 [기존 코드에서 Python 프로젝트를 만듭니다](quickstart-01-python-in-visual-studio-project-from-existing-code.md).

## <a name="the-python-environments-window"></a>Python 환경 창

*(이 섹션에 표시된 스크린샷은 Visual Studio 15.8를 나타냅니다. Visual Studio의 버전에 따라 UI가 다르게 표시될 수 있습니다.)*

Visual Studio에서 인식하는 환경이 **Python 환경** 창에 표시됩니다. 창을 열려면 다음 방법 중 하나를 사용합니다.

- **보기** > **다른 창** > **Python 환경** 메뉴 명령을 선택합니다.
- **솔루션 탐색기**에서 프로젝트의 **Python 환경** 노드를 마우스 오른쪽 단추로 클릭하고 **모든 Python 환경 보기**를 선택합니다.

    ![솔루션 탐색기에서 모든 환경 명령 보기](media/environments-view-all.png)

두 경우 모두 **Python 환경** 창은 **솔루션 탐색기**와 함께 나타납니다.

![Python 환경 창](media/environments-default-view.png)

Visual Studio는 레지스트리(다음 [PEP 514](https://www.python.org/dev/peps/pep-0514/))와 함께 가상 환경 및 Conda 환경([환경 유형](#types-of-environments) 참조)을 사용하여 설치된 글로벌 환경을 검색합니다. 목록에 원하는 환경이 표시되지 않으면 [기존 환경 수동 식별](#manually-identify-an-existing-environment)을 참조하세요.

목록에서 환경을 선택하는 경우 Visual Studio는 **개요** 탭에 해당 환경에 대한 다양한 속성과 명령을 표시합니다. 예를 들어 위의 이미지에서 인터프리터의 위치가 *C:\Python36-32*임을 알 수 있습니다. **개요** 탭 아래에 있는 네 개의 명령은 각각 인터프리터가 실행 중인 명령 프롬프트를 엽니다. 자세한 내용은 [Python 환경 창 탭 참조 - 개요](python-environments-window-tab-reference.md#overview-tab)를 참조하세요.

환경 목록 아래의 드롭다운 목록을 사용하여 **패키지** 및 **IntelliSense**와 같은 다른 탭으로 전환합니다. 이러한 탭은 [Python 환경 창 탭 참조](python-environments-window-tab-reference.md)에도 설명되어 있습니다.

환경을 선택하면 모든 프로젝트에 대한 해당 관계는 변경되지 않습니다. 목록에서 굵게 표시된 기본 환경은 Visual Studio가 모든 새 프로젝트에 대해 사용하는 환경입니다. 새 프로젝트에서 다른 환경을 사용하려면 **이 환경을 새 프로젝트의 기본 환경으로 설정** 명령을 사용합니다. 프로젝트의 컨텍스트 내에서 항상 특정한 환경을 선택할 수 있습니다. 자세한 내용은 [프로젝트의 환경 선택](selecting-a-python-environment-for-a-project.md)을 참조하세요.

나열된 각 환경의 오른쪽에는 해당 환경에 대한 **대화형** 창을 여는 컨트롤이 있습니다. Visual Studio 2017 15.5 이전에서 해당 환경의 IntelliSense 데이터베이스를 새로 고치는 다른 컨트롤이 표시됩니다. 데이터베이스에 대한 세부 정보는 [환경 창 탭 참조](python-environments-window-tab-reference.md#intellisense-tab)를 참조하세요.

> [!Tip]
> **Python 환경** 창을 충분히 넓게 확장하면 작업하기에 더 편리한 환경을 보다 자세히 볼 수 있습니다.
>
> ![Python 환경 창 확장된 보기](media/environments-expanded-view.png)

> [!Note]
> Visual Studio에서는 system-site-packages 옵션을 적용하지만 Visual Studio 내에 이를 변경하는 방법은 제공하지 않습니다.

|   |   |
|---|---|
| ![비디오에 대한 비디오 카메라 아이콘](../install/media/video-icon.png "비디오 보기") | Visual Studio의 Python 환경에 대한 [비디오(Microsoft Virtual Academy)를 시청](https://mva.microsoft.com/en-US/training-courses/python-tools-for-visual-studio-2017-18121?l=qrDmN4LWE_8305918567)하세요(2분 35초).|

### <a name="what-if-no-environments-appear"></a>환경이 나타나지 않으면 어떻게 하나요?

환경이 나타나지 않으면 Visual Studio가 표준 위치에서 Python 설치를 검색하지 못한 것입니다. 예를 들어 Visual Studio 2017을 설치했지만 Python 워크로드에 대한 설치 관리자 옵션에서 모든 인터프리터 옵션을 선택 취소했을 수 있습니다. 마찬가지로 Visual Studio 2015 이전을 설치했지만 인터프리터를 수동으로 설치하지 않았을 수 있습니다([Python 인터프리터 설치](installing-python-interpreters.md) 참조).

컴퓨터에 Python 인터프리터가 있지만 Visual Studio(모든 버전)가 이를 검색하지 못하는 경우 **+ 사용자 지정** 명령을 사용하여 해당 위치를 수동으로 지정합니다. 다음 섹션인 [기존 환경 수동 식별](#manually-identify-an-existing-environment)을 참조하세요.

> [!Tip]
> Visual Studio는 python.org의 설치 관리자를 사용하여 Python2.7.11을 2.7.14로 업그레이드하는 경우와 같은 기존 인터프리터의 업데이트를 검색합니다. 설치 과정에서 **Python 환경** 목록에서 이전 환경이 사라진 후 업데이트가 그 자리에 나타납니다.
>
> 그러나 파일 시스템을 사용하여 인터프리터 및 해당 환경을 수동으로 이동할 경우 Visual Studio에서는 새 위치를 알 수 없습니다. 자세한 내용은 [인터프리터 이동](installing-python-interpreters.md#move-an-interpreter)을 참조하세요.

### <a name="types-of-environments"></a>환경 유형

Visual Studio는 글로벌 환경, 가상 환경 및 Conda 환경을 사용할 수 있습니다.

#### <a name="global-environments"></a>글로벌 환경

각 Python 설치(예: Python 2.7, Python 3.6, Python 3.7, Anaconda 4.4.0 등은 [Python 인터프리터 설치](installing-python-interpreters.md) 참조)는 고유한 *글로벌 환경*을 유지 관리합니다. 각 환경은 특정 Python 인터프리터, 표준 라이브러리, 사전 설치된 패키지 집합 및 해당 환경이 활성화된 상태에서 설치하는 모든 추가 패키지로 구성됩니다. 패키지를 전역 환경에 설치하면 해당 환경을 사용하는 모든 프로젝트에서 사용할 수 있습니다. 환경이 파일 시스템의 보호 영역(예: *c:\program files* 내)에 있는 경우 패키지를 설치하려면 관리자 권한이 필요합니다.

전역 환경은 컴퓨터의 모든 프로젝트에서 사용할 수 있습니다. Visual Studio에서는 특별히 프로젝트별로 다른 항목을 선택하지 않는 한 하나의 전역 환경을 모든 프로젝트에 사용되는 기본값으로 선택합니다. 자세한 내용은 [프로젝트의 환경 선택](selecting-a-python-environment-for-a-project.md)을 참조하세요.

#### <a name="virtual-environments"></a>가상 환경

글로벌 환경에서 작업하면 쉽게 시작할 수 있다 해도 해당 환경은 시간이 지남에 따라 다른 프로젝트에 설치한 많은 다른 패키지와 겹쳐 복잡해집니다. 이러한 혼란은 알려진 버전을 사용하여 특정 집합의 패키지에 대해 빌드 서버 또는 웹 서버에서 설정하는 환경의 종류인 애플리케이션을 철저히 테스트하는 것을 어렵게 합니다. 두 프로젝트에 호환되지 않는 패키지 또는 동일한 패키지의 다른 버전이 필요한 경우 충돌이 발생할 수 있습니다.

이러한 이유로 개발자는 종종 프로젝트에 대한 *가상 환경*을 만듭니다. 가상 환경은 특정 인터프리터가 포함된 프로젝트의 하위 폴더입니다. 가상 환경이 활성화되면 설치한 모든 패키지는 해당 환경의 하위 폴더에만 설치됩니다. 그런 다음, 해당 환경 내에서 Python 프로그램을 실행하면 이 프로그램이 해당 특정 패키지에 대해서만 실행되는지 알 수 있습니다.

Visual Studio는 프로젝트에 대한 가상 환경을 만드는 작업을 직접 지원합니다. 예를 들어 *requirements.txt*가 포함된 프로젝트를 열거나 해당 파일이 포함된 템플릿에서 프로젝트를 만드는 경우 Visual Studio에서는 사용자에게 가상 환경을 자동으로 만들고 해당 종속성을 설치하게 합니다.

열린 프로젝트 내에서 언제든 새 가상 환경을 만들 수 있습니다. **솔루션 탐색기**에서 프로젝트 노드를 확장하고 **Python 환경** 노드를 마우스 오른쪽 단추로 클릭하고 “가상 환경 추가”를 선택합니다. 자세한 내용은 [가상 환경 만들기](selecting-a-python-environment-for-a-project.md#create-a-virtual-environment)를 참조하세요.

Visual Studio에서는 쉽게 다른 컴퓨터에서 환경을 다시 만들 수 있도록 가상 환경에서 *requirements.txt* 파일을 생성하는 명령을 제공합니다. 자세한 내용은 [가상 환경 사용](selecting-a-python-environment-for-a-project.md#use-virtual-environments)을 참조하세요.

#### <a name="conda-environments"></a>Conda 환경

Conda 환경은 `conda` 도구를 사용하거나 Visual Studio 버전 2017 15.7 이상에서 통합 Conda 관리를 사용하여 만듭니다. Anaconda 또는 Miniconda가 필요합니다. Anaconda는 Visual Studio 설치 관리자를 통해 지원됩니다. [설치 - Visual Studio 2017](installing-python-support-in-visual-studio.md#visual-studio-2017)을 참조하세요.

1. **Python 환경** 창에서 **+ Conda 환경 만들기**를 선택하면 **새 Conda 환경 만들기** 탭이 열립니다.

    ![새 Conda 환경의 탭 만들기](media/environments-conda-1.png)

1. **이름** 필드에서 환경의 이름을 입력하고, **Python** 필드에서 기본 Python 인터프리터를 선택하고 **만들기**를 선택합니다.

1. **출력** 창에서는 생성이 완료되면 몇 가지 CLI 지침을 사용하여 새 환경에 대한 진행률을 보여줍니다.

    ![성공적으로 Conda 환경 만들기](media/environments-conda-2.png)

1. [프로젝트의 환경 선택](selecting-a-python-environment-for-a-project.md)에 설명된 대로 다른 환경에서 수행한 것처럼 Visual Studio 내에서 프로젝트의 Conda 환경을 활성화할 수 있습니다.

1. 환경에서 패키지를 설치하려면 [패키지 탭](python-environments-window-tab-reference.md#packages-tab)을 사용합니다.

> [!Note]
> Conda 환경을 사용하는 최상의 결과는 Conda 4.4.8 이상을 사용합니다(Conda 버전은 Anaconda 버전과 다름). Visual Studio 2017 설치 관리자에서 Anaconda 5.1을 설치합니다.

Conda 환경이 저장된 Conda 버전 및 기타 정보를 보려면 Anaconda 명령 프롬프트(즉, Anaconda가 경로에 있는 명령 프롬프트)에서 `conda info`를 실행합니다.

```cli
conda info
```

Conda 환경 폴더가 다음과 같이 표시됩니다.

```output
       envs directories : c:\anaconda3\envs
                          C:\Users\user\AppData\Local\conda\conda\envs
                          C:\Users\user\.conda\envs
```

Conda 환경을 프로젝트와 저장하지 않았기 때문에 글로벌 환경에서 비슷하게 작동합니다. 예를 들어 새 패키지를 conda 환경에 설치하면 해당 환경을 사용하는 모든 프로젝트에서 해당 패키지를 사용할 수 있습니다.

Visual Studio 2017 버전 15.6 이전의 경우 [기존 환경 수동 식별](#manually-identify-an-existing-environment) 아래에 설명된 대로 수동으로 지정하여 Conda 환경을 사용할 수 있습니다.

Visual Studio 2017 버전 15.7 이상에서는 Conda 환경을 자동으로 검색하고 다음 섹션에 설명된 대로 **Python 환경** 창을 표시합니다.

## <a name="manually-identify-an-existing-environment"></a>기존 환경 수동 식별

Visual Studio 2017 버전 15.6 이전의 Conda 환경을 포함하여 비표준 위치에 설치된 환경을 식별하려면 다음 단계를 수행합니다.

1. **Python 환경** 창에서 **+ 사용자 지정**을 선택하면 **구성** 탭이 열립니다.

    ![새 사용자 지정 환경의 기본 보기](media/environments-custom-1.png)

1. **설명** 필드에 환경에 대한 이름을 입력합니다.

1. **접두사 경로** 필드에 인터프리터의 경로를 입력하거나 찾습니다(**...** 사용).

1. Visual Studio가 해당 위치(예: conda 환경에 대해 아래에 표시된 경로)에서 Python 인터프리터를 검색할 경우 **자동 검색** 명령을 사용할 수 있습니다. **자동 검색**을 선택하면 나머지 필드가 채워집니다. 해당 필드를 수동으로 완료할 수도 있습니다.

    ![자동 검색 명령 사용](media/environments-custom-2.png)

    ![자동 검색을 사용한 후 환경 필드 완료](media/environments-custom-3.png)

1. 필드에 원하는 값이 포함되면 **적용**을 선택하여 구성을 저장합니다. 이제 Visual Studio 내에서 다른 환경과 같이 해당 환경을 사용할 수 있습니다.

1. 수동으로 식별된 환경을 제거해야 하는 경우 **구성** 탭에서 **제거** 명령을 선택합니다. 자동 감지 환경에서는 이 옵션을 제공하지 않습니다. 자세한 내용은 [구성 탭](python-environments-window-tab-reference.md#configure-tab)을 참조하세요.

## <a name="fix-or-delete-invalid-environments"></a>잘못된 환경 수정 또는 삭제

Visual Studio에서 환경에 대한 레지스트리 항목을 찾았지만 인터프리터에 대한 경로가 올바르지 않은 경우 **Python 환경** 창은 취소선 글꼴을 사용하여 이름을 표시합니다.

![잘못된 환경을 보여주는 Python 환경 창](media/environments-invalid-entry.png)

유지할 환경을 수정하려면 먼저 해당 설치 관리자의 **복구** 프로세스를 사용해 보세요. 예를 들어 표준 Python 3.x에 대한 설치 관리자에는 해당 옵션이 포함됩니다.

복구 옵션이 포함되지 않은 환경을 수정하거나 잘못된 환경을 제거하려면 다음 단계를 사용하여 레지스트리를 직접 수정합니다. Visual Studio는 레지스트리를 변경하는 경우 **Python 환경** 창을 자동으로 업데이트합니다.

1. *regedit.exe*를 실행합니다.
1. 32비트 인터프리터의 경우 **HKEY_LOCAL_MACHINE\SOFTWARE\Python**로 이동하고 64비트 인터프리터의 경우 **HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Python**으로 이동합니다. IronPython의 경우 대신 **IronPython**을 찾습니다.
1. CPython의 경우 **PythonCore** 또는 Anaconda의 경우 **ContinuumAnalytics**와 같은 분포와 일치하는 노드를 확장합니다. IronPython의 경우 버전 번호 노드를 확장합니다.
1. **InstallPath** 노드 아래의 값을 검사합니다.

    ![표준 CPython 설치를 위한 레지스트리 항목](media/environments-registry-entries.png)

    - 컴퓨터에 여전히 환경이 있는 경우 **ExecutablePath**의 값을 현재 위치로 변경합니다. 필요에 따라 **(기본값)** 및 **WindowedExecutablePath** 값을 수정합니다.
    - 환경이 컴퓨터에 더 이상 존재하지 않고 **Python 환경** 창에서 제거하려는 경우 위의 이미지에서 **3.6**과 같은 **InstallPath**의 부모 노드를 삭제합니다.

## <a name="see-also"></a>참고 항목

- [Python 인터프리터 설치](installing-python-interpreters.md)
- [프로젝트의 인터프리터 선택](selecting-a-python-environment-for-a-project.md)
- [종속성에 대해 requirements.txt 사용](managing-required-packages-with-requirements-txt.md)
- [검색 경로](search-paths.md)
- [Python 환경 창 참조](python-environments-window-tab-reference.md)

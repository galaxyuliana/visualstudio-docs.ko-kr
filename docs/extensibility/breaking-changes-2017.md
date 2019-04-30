---
title: Visual Studio 2017 확장성의 주요 변경 내용
titleSuffix: ''
ms.date: 11/09/2016
ms.topic: conceptual
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
monikerRange: vs-2017
ms.openlocfilehash: e7363a0779721e4fb36106d6ee77324c341517ba
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62926837"
---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 확장성의 변경 내용

Visual Studio 2017은 제공 된 [빠르고 가벼운 Visual Studio 설치 환경을](https://devblogs.microsoft.com/visualstudio/faster-leaner-visual-studio-installer) 사용자에 게 큰 워크 로드 및 기능을 제공 하는 동안 사용자 시스템에 Visual Studio의 영향을 줄여 주는 설치 합니다. 이러한 향상 된이 기능을 지원 하려면 몇 가지 혁신적인 변화가 포함 하 여 확장성 모델에 변경 내용을 만들었습니다. 이 문서에서는 이러한 변경 내용 및 해결을 수행할 수 있는 작업의 기술 세부 정보를 설명 합니다.

> [!NOTE]
> 일부 정보가 시점에서 구현 정보 이며 나중에 변경할 수 있습니다.

## <a name="changes-affecting-vsix-format-and-installation"></a>VSIX 형식 및 설치에 영향을 주는 변경 내용

VSIX v3를 도입 visual Studio 2017 (버전 3) 형식은 간단한 설치 환경을 지원 하도록 합니다.

다음과 같은 VSIX 형식 변경

* 설치 필수 구성 요소의 선언입니다. 약속 fast-Visual Studio 설치, 간단한 전달할 설치 관리자에 게 더 많은 구성 옵션 이제 제공 합니다. 결과적으로, 기능 및 확장에서 필요한 구성 요소가 설치 되어 있는지를 확장 해야 해당 종속성을 선언 합니다.

  * Visual Studio 2017 설치 관리자는 자동으로 획득 및 확장 설치의 일부로 사용자에 대해 필요한 구성 요소 설치를 제공 합니다.
  * 사용자는 또한 빌드하지 않은 새 VSIX v3 형식을 사용 하 여 대상 버전 15.0으로 매니페스트에 표시 된 경우에 확장을 설치 하려고 할 때 경고 메시지가 표시 됩니다.

* VSIX 형식에 대 한 향상 된 기능입니다. 제공 하는 [영향이 적은 설치](https://devblogs.microsoft.com/visualstudio/anatomy-of-a-low-impact-visual-studio-install) 또한 side-by-side-설치를 지 원하는 Visual studio를 더 이상 시스템 레지스트리에 대부분의 구성 데이터를 저장 하 고 Visual Studio 관련 어셈블리를 GAC에서 이동 합니다. 또한 늘렸습니다 VSIX 형식 및 VSIX 설치 엔진의 기능 일부 설치 유형에 대 한 확장을 설치 하지 않고는 MSI 또는 EXE를 사용할 수 있습니다.

새로운 기능에는 다음이 포함 됩니다.

* 지정된 된 Visual Studio 인스턴스를 등록 합니다.
* 외부에서 설치를 [extensions 폴더](set-install-root.md)합니다.
* 프로세서 아키텍처를 검색 합니다.
* 언어 구분 된 언어 팩에 대 한 종속성입니다.
* 사용 하 여 설치 [NGEN 지원](ngen-support.md)합니다.

## <a name="build-an-extension-for-visual-studio-2017"></a>Visual Studio 2017 용 확장 빌드

새 작성 하기 위한 도구 디자이너 VSIX v3 매니페스트 형식은 Visual Studio 2017에서 사용할 수 있습니다. 함께 제공 되는 문서를 참조 하세요. [방법: Visual Studio 2017로 확장성 프로젝트 마이그레이션](how-to-migrate-extensibility-projects-to-visual-studio-2017.md) 디자이너 도구를 사용 하 여 또는 수동 업데이트할 프로젝트에 대 한 자세한 내용은 및 매니페스트를 VSIX v3 확장을 개발 합니다.

## <a name="change-visual-studio-user-data-path"></a>변경 내용: Visual Studio 사용자 데이터 경로

이전에 Visual Studio의 각 주요 릴리스에서 하나만 설치할 각 컴퓨터에 존재할 수 있습니다. Visual Studio 2017의 side-by-side-설치를 지원 하려면 Visual Studio에 대 한 여러 사용자 데이터 경로 사용자의 컴퓨터에 존재할 수 있습니다.

Visual Studio 프로세스 내에서 실행 되는 코드는 Visual Studio Settings Manager를 사용 하도록 업데이트 되어야 합니다. Visual Studio 프로세스 외부에서 실행 되는 코드에서 특정 Visual Studio 설치의 사용자 경로 찾을 수 [지침에 따라](locating-visual-studio.md)합니다.

## <a name="change-global-assembly-cache-gac"></a>변경 내용: 전역 어셈블리 캐시 (GAC)

대부분의 Visual Studio 핵심 어셈블리를 GAC에 더 이상 설치 됩니다. Visual Studio 프로세스에서 실행 되는 코드 런타임에 필요한 어셈블리를 찾을 수 있도록 다음 변경 내용이 적용 됩니다.

> [!NOTE]
> [INSTALLDIR] 아래 Visual Studio의 설치 루트 디렉터리를 가리킵니다. *VSIXInstaller.exe* 는 자동으로이 채우는 하지만 사용자 지정 배포 코드를 작성 하려면 읽어보세요 [Visual Studio 찾기](locating-visual-studio.md)합니다.

* GAC에만 설치 된 어셈블리:

   이러한 어셈블리는 이제 설치 <em>[INSTALLDIR] \Common7\IDE\*, * [INSTALLDIR] \Common7\IDE\PublicAssemblies</em> 하거나 *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*합니다. 이러한 폴더를 사용 하면 Visual Studio 프로세스의 검색 경로에 속합니다.

* 비 검색 경로 GAC에 설치 된 어셈블리:

   * GAC의 복사본은 설치 프로그램에서 제거 되었습니다.
   * A *.pkgdef* 파일 어셈블리에 대 한 코드 베이스 엔트리를 지정 하려면 추가 되었습니다.

      예를 들어:

      ```xml
      [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
      "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
      "publicKeyToken"="Public Key Token"
      "culture"="neutral"
      "version"=15.0.0.0
      ```

      Visual Studio pkgdef 하위 시스템은 런타임 시 Visual Studio 프로세스의 런타임 구성 파일에 이러한 항목을 병합 (아래 *[VSAPPDATA]\devenv.exe.config*)으로 [ `<codeBase>` ](/dotnet/framework/configure-apps/file-schema/runtime/codebase-element) 요소입니다. 이것이 경로 검색을 통해 검색을 방지 하기 때문에 Visual Studio 프로세스에 어셈블리를 찾을 수 있도록 권장 되는 방법입니다.

### <a name="reacting-to-this-breaking-change"></a>이 주요 변경에 대응

* 경우 확장은 Visual Studio 프로세스 내에서 실행 됩니다.

   * 코드는 Visual Studio 핵심 어셈블리를 찾을 수 됩니다.
   * 사용 하는 것이 좋습니다는 *.pkgdef* 필요한 경우 어셈블리에 대 한 경로 지정 하는 파일입니다.

* 확장은 Visual Studio 프로세스 외부에서 실행 되 하는 경우:

   아래에서 Visual Studio 핵심 어셈블리에 대 한 확인 하는 것이 좋습니다 <em>[INSTALLDIR] \Common7\IDE\*, * [INSTALLDIR] \Common7\IDE\PublicAssemblies</em> 또는 *[INSTALLDIR] \Common7\IDE\PrivateAssemblies*구성 파일 또는 어셈블리 확인자를 사용 하 여 합니다.

## <a name="change-reduce-registry-impact"></a>변경 내용: 레지스트리 영향 줄이기

### <a name="global-com-registration"></a>전역 COM 등록

* 이전에 Visual Studio는 네이티브 COM 등록을 지원 하기 위해 HKEY_CLASSES_ROOT 및 HKEY_LOCAL_MACHINE 하이브에 여러 레지스트리 키를 설치 합니다. 이 영향을 제거 하려면 Visual Studio는 이제 사용 [COM 구성 요소에 대 한 등록이 필요 없는 활성화](https://msdn.microsoft.com/library/ms973913.aspx)합니다.
* 결과적으로 대부분의 TLB / OLB %ProgramFiles (x86) %\Common Files\Microsoft Shared\MSEnv DLL 파일은 더 이상 Visual Studio에서 기본적으로 설치 됩니다. 이러한 파일은 이제 Visual Studio 호스트 프로세스에서 사용 하는 해당 등록이 필요 없는 COM 매니페스트를 사용 하 여 [INSTALLDIR] 아래에서 설치 됩니다.
* 결과적으로, Visual Studio COM 인터페이스에 대 한 전역 COM 등록을 사용 하는 외부 코드는 이러한 등록을 찾을 더 이상 됩니다. Visual Studio 프로세스 내에서 실행 되는 코드에는 차이가 표시 되지 않습니다.

### <a name="visual-studio-registry"></a>Visual Studio 레지스트리

* Visual Studio 시스템에 여러 레지스트리 키를 설치 하는 이전에 **HKEY_LOCAL_MACHINE** 하 고 **HKEY_CURRENT_USER** Visual Studio 관련 키 아래 하이브:

  * **HKLM\Software\Microsoft\VisualStudio\{Version}**: MSI 설치 관리자 및 컴퓨터별 확장에서 만든 레지스트리 키입니다.
  * **HKCU\Software\Microsoft\VisualStudio\{Version}**: 사용자 관련 설정을 저장 하려면 Visual Studio에서 만든 레지스트리 키입니다.
  * **HKCU\Software\Microsoft\VisualStudio\{Version}_Config**: 위의 Visual Studio HKLM 키와 레지스트리 키의 복사본에서 병합 *.pkgdef* 파일 확장명으로 합니다.

* 레지스트리에 대 한 영향을 줄이기 위해 Visual Studio는 이제 사용 합니다 [RegLoadAppKey](/windows/desktop/api/winreg/nf-winreg-regloadappkeya) 레지스트리 키 아래에 있는 개인 이진 파일에 저장할 수는 함수 *[VSAPPDATA]\privateregistry.bin*합니다. Visual Studio 관련 키의 매우 작은 수만 시스템 레지스트리를 유지합니다.
* Visual Studio 프로세스 내에서 실행 되는 기존 코드를 받지 않습니다. Visual Studio은 개인 레지스트리에 HKCU Visual Studio 관련 키 아래의 모든 레지스트리 작업을 리디렉션합니다. 시스템 레지스트리를 사용 하 여 읽기 및 쓰기 다른 레지스트리 위치를 계속 합니다.
* 외부 코드는 Visual Studio 레지스트리 항목에 대 한이 파일에서 읽고 로드 해야 합니다.

### <a name="react-to-this-breaking-change"></a>이 주요 변경에 대응

* 외부 코드도 COM 구성 요소에 대 한 등록이 필요 없는 활성화를 사용 하도록 변환 됩니다.
* 외부 구성 요소는 Visual Studio 위치를 찾을 수 있습니다 [지침에 따라](https://devblogs.microsoft.com/setup/changes-to-visual-studio-15-setup)합니다.
* 외부 구성 요소를 사용 하는 것이 좋습니다 합니다 [외부 Settings Manager](/dotnet/api/microsoft.visualstudio.settings.externalsettingsmanager) Visual Studio 레지스트리 키에 직접 읽고 쓰는 대신 합니다.
* 여부를 구성 요소 확장을 사용 하는 수 구현한 또 다른 방법은 등록에 대 한 확인 합니다. 예를 들어, 디버거 확장 새 활용 하는 일을 할 수 있습니다 [msvsmon JSON 파일 COM 등록](migrate-debugger-COM-registration.md)합니다.

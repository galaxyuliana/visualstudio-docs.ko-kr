---
title: 프로젝트 디자이너, 빌드 페이지(C#) | Microsoft 문서
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- cs.ProjectPropertiesBuild
helpviewer_keywords:
- Build options [C#]
- Project Designer, Build page
ms.assetid: 77ff1bfc-d633-4634-ba29-9afdb6d7e362
caps.latest.revision: 47
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: aa4eea56321d636efb6458b52b8ad2f271e439ce
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65673842"
---
# <a name="build-page-project-designer-c"></a>프로젝트 디자이너, 빌드 페이지(C#)
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

**프로젝트 디자이너**의 **빌드** 페이지를 사용하여 프로젝트의 빌드 구성 속성을 지정합니다. 이 페이지는 [!INCLUDE[csprcs](../../includes/csprcs-md.md)] 프로젝트에만 적용됩니다.  
  
 **빌드** 페이지에 액세스하려면 **솔루션 탐색기**에서 프로젝트 노드(**솔루션** 노드 아님)를 선택합니다. 그런 다음 메뉴 모음에서 **프로젝트**, **속성**을 선택합니다. [프로젝트 디자이너]가 나타나면 **빌드** 탭을 클릭합니다.  
  
 [!INCLUDE[note_settings_general](../../includes/note-settings-general-md.md)]  
  
## <a name="configuration-and-platform"></a>구성 및 플랫폼  
 다음 옵션을 사용하여 표시하거나 수정할 구성 및 플랫폼을 선택할 수 있습니다.  
  
> [!NOTE]
> 단순화된 빌드 구성을 사용하면 프로젝트 시스템에서 디버그 버전을 빌드할지 아니면 릴리스 버전을 빌드할지 결정합니다. 따라서 이러한 옵션이 표시되지 않습니다. 자세한 내용은 [디버그 및 릴리스 프로젝트 구성](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e)을 참조하세요.  
  
 **구성**  
 표시하거나 수정할 구성 설정을 지정합니다. **활성(디버그)** (기본값), **디버그**, **릴리스** 또는 **모든 구성** 중에서 설정을 선택할 수 있습니다.  
  
 **플랫폼**  
 표시하거나 수정할 플랫폼 설정을 지정합니다. 기본 설정은 **활성(모든 CPU)** 입니다. **구성 관리자**를 사용하여 활성 플랫폼을 변경할 수 있습니다. 자세한 내용은 [방법: 구성 만들기 및 편집](../../ide/how-to-create-and-edit-configurations.md)을 참조하세요.  
  
## <a name="general"></a>일반  
 다음 옵션을 사용하여 여러 C# 컴파일러 설정을 구성할 수 있습니다.  
  
 **조건부 컴파일 기호**  
 조건부 컴파일을 수행할 기호를 지정합니다. 기호를 세미콜론(“;”)으로 구분합니다. 자세한 내용은 [/define(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/f17d7b4d-82d0-4133-8563-68cced1cac6e)을 참조하세요.  
  
 **DEBUG 상수 정의**  
 앱의 모든 소스 코드 파일에서 DEBUG를 기호로 정의합니다. 이 옵션을 선택하는 것은 `/define:DEBUG` 명령줄 옵션을 사용하는 것과 같습니다.  
  
 **TRACE 상수 정의**  
 앱의 모든 소스 코드 파일에서 TRACE를 기호로 정의합니다. 이 옵션을 선택하는 것은 `/define:TRACE` 명령줄 옵션을 사용하는 것과 같습니다.  
  
 **대상 CPU**  
 출력 파일의 대상으로 프로세서를 지정합니다. 32비트 Intel 호환 프로세서의 경우 **x86**을 선택하고, 64비트 Intel 호환 프로세서의 경우 **x64**를 선택하고, ARM 프로세서의 경우 **ARM**을 선택하고, 임의 프로세스를 허용하도록 지정하려면 **임의 CPU**를 선택합니다. **임의 CPU**는 프로젝트의 기본값입니다. 하드웨어의 가장 광범위한 범위에서 애플리케이션을 실행할 수 있기 때문입니다.  
  
 자세한 내용은 [/platform(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/c290ff5e-47f4-4a85-9bb3-9c2525b0be04)을 참조하세요.  
  
 **32비트 선호**  
 **32비트 선호** 확인란을 선택하면 애플리케이션은 Windows 32비트 및 64비트 버전에서 모두 32비트 애플리케이션으로 실행됩니다. 이 확인란을 선택 취소하면 애플리케이션은 32비트 버전 Windows에서는 32비트 애플리케이션으로, 64비트 버전 Windows에서는 64비트 애플리케이션으로 실행됩니다.  
  
 애플리케이션을 64비트 애플리케이션으로 실행하면 포인터 크기가 두 배가 되고 32비트 전용인 다른 라이브러리에 대한 호환성 문제가 발생할 수 있습니다. 4GB 이상의 메모리가 필요하거나 64비트 명령으로 성능을 크게 향상할 수 있는 경우에만 64비트 애플리케이션을 실행하는 것이 좋습니다.  
  
 이 확인란은 다음 조건을 충족하는 경우에만 사용할 수 있습니다.  
  
- **빌드 페이지**에서 **플랫폼 대상** 목록이 **임의 CPU**로 설정되어 있습니다.  
  
- **애플리케이션 페이지**에서 **출력 형식** 목록의 프로젝트가 애플리케이션으로 지정됩니다.  
  
- **애플리케이션 페이지**에서 **대상 프레임워크** 목록이 .NET Framework 4.5로 지정됩니다.  
  
  **안전하지 않은 코드 허용**  
  컴파일에 [unsafe](https://msdn.microsoft.com/library/7e818009-1c6e-4b9e-b769-3728a01586a0) 키워드를 사용하는 코드를 허용합니다. 자세한 내용은 [/unsafe(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/fdb77ed9-da03-45bd-bb7f-250704da1bcc)를 참조하세요.  
  
  **코드 최적화**  
  컴파일러에서 더 작지만 빠르고 효율적인 출력 파일을 만들기 위해 수행하는 최적화 기능을 사용하거나 사용하지 않도록 설정합니다. 자세한 내용은 [/optimize(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/6dd5b6f2-cd1d-4593-a9f4-1c2ed9404ca0)를 참조하세요.  
  
## <a name="errors-and-warnings"></a>오류 및 경고  
 다음 설정은 빌드 프로세스에 대한 오류 및 경고 옵션을 구성하는 데 사용됩니다.  
  
 **경고 수준**  
 컴파일러 경고에 대한 표시 수준을 지정합니다. 자세한 내용은 [/warn(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/5f80ff59-4991-4382-9f9a-77da18446e71)을 참조하세요.  
  
 **경고 표시 안 함**  
 컴파일러에서 하나 이상의 경고를 생성하지 않도록 합니다. 여러 경고 번호를 쉼표 또는 세미콜론으로 구분합니다. 자세한 내용은 [/nowarn(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/6dcbc5e8-ae67-4566-9df3-f63cfdd9c4e4)을 참조하세요.  
  
## <a name="treat-warnings-as-errors"></a>경고를 오류로 처리  
 다음 설정은 오류로 처리되는 경고를 지정하는 데 사용됩니다. 빌드에서 경고가 발생할 때 오류를 반환하는 조건을 지정하려면 다음 옵션 중 하나를 선택합니다. 자세한 내용은 [/warnaserror(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/04680ec3-08d6-4e2e-a274-38310e10e33c)를 참조하세요.  
  
 **없음**  
 경고를 오류로 처리하지 않습니다.  
  
 **특정 경고**  
 지정된 경고를 오류로 처리합니다. 여러 경고 번호를 쉼표 또는 세미콜론으로 구분합니다.  
  
 **All**  
 모든 경고를 오류로 처리합니다.  
  
## <a name="output"></a>Output  
 다음 설정은 빌드 프로세스에 대한 출력 옵션을 구성하는 데 사용됩니다.  
  
 **출력 경로**  
 프로젝트 구성에 사용할 출력 파일의 위치를 지정합니다. 이 상자에 빌드 출력의 경로를 입력하거나 **찾아보기** 단추를 선택하여 경로를 지정합니다. 경로는 상대 경로입니다. 절대 경로를 입력하면 상대 경로로 저장됩니다. 기본 경로는 bin\Debug 또는 bin\Release\\입니다. 자세한 내용은 [디버그 및 릴리스 프로젝트 구성](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e)을 참조하세요.  
  
 단순화된 빌드 구성을 사용하면 프로젝트 시스템에서 디버그 버전을 빌드할지 아니면 릴리스 버전을 빌드할지 결정합니다. **디버그** 메뉴(F5)의 **빌드** 명령은 지정한 **출력 경로**에 관계없이 빌드를 디버그 위치에 삽입합니다. 그러나 **빌드** 메뉴의 **빌드** 명령은 경로를 지정한 위치에 삽입합니다. 자세한 내용은 [디버그 및 릴리스 프로젝트 구성](https://msdn.microsoft.com/0440b300-0614-4511-901a-105b771b236e)을 참조하세요.  
  
 **XML 문서 파일**  
 문서 주석을 처리할 대상 파일의 이름을 지정합니다. 자세한 내용은 [/doc(C# 컴파일러 옵션)](https://msdn.microsoft.com/library/849eea59-c936-4311-bad8-d07404480f2a)를 참조하세요.  
  
 **COM interop 등록**  
 관리되는 애플리케이션이 COM 개체가 관리되는 애플리케이션과 상호 작용할 수 있도록 하는 COM 개체(COM 호출 가능 래퍼)를 표시하도록 지정합니다. **COM interop 등록** 속성을 사용할 수 있으려면 이 애플리케이션에 대한 **프로젝트 디자이너**의 [애플리케이션 페이지](../../ide/reference/application-page-project-designer-visual-basic.md)에서 **출력 형식** 속성을 **클래스 라이브러리**로 설정해야 합니다. [!INCLUDE[csprcs](../../includes/csprcs-md.md)] 애플리케이션에 포함하고 COM 개체로 표시할 수 있는 클래스 예제는 [COM 클래스 예제](https://msdn.microsoft.com/library/6504dea9-ad1c-4993-a794-830fec5270af)를 참조하세요.  
  
 **serialization 어셈블리 생성**  
 XML serialization 어셈블리를 만드는 데 XML 직렬 변환기 생성기 도구(Sgen.exe)를 사용할지 여부를 지정합니다. 코드에서 형식을 직렬화하는 데 <xref:System.Xml.Serialization.XmlSerializer> 클래스를 사용한 경우 serialization 어셈블리가 해당 클래스의 시작 성능을 향상할 수 있습니다. 기본적으로 이 옵션은 **자동**으로 설정됩니다. 이 설정은 코드에서 형식을 XML로 인코딩하는 데 <xref:System.Xml.Serialization.XmlSerializer>를 사용한 경우에만 serialization 어셈블리가 생성되도록 지정합니다. **끄기**는 코드에서 <xref:System.Xml.Serialization.XmlSerializer>를 사용하는지와 관계없이 serialization 어셈블리가 생성되지 않도록 지정합니다. **켜기**는 serialization 어셈블리가 항상 생성되도록 지정합니다. Serialization 어셈블리의 이름은 `TypeName`.XmlSerializers.dll로 지정됩니다. 자세한 내용은 [XML Serializer 생성기 도구(Sgen.exe)](https://msdn.microsoft.com/library/cc1d1f1c-fb26-4be9-885a-3fe84c81cec6)를 참조하세요.  
  
 **고급**  
 [고급 빌드 설정 대화 상자(C#)](../../ide/reference/advanced-build-settings-dialog-box-csharp.md) 대화 상자를 표시하려면 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 속성 참조](../../ide/reference/project-properties-reference.md)   
 [C# 컴파일러 옵션](https://msdn.microsoft.com/library/d3403556-1816-4546-a782-e8223a772e44)

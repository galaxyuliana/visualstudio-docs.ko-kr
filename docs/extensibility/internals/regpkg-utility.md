---
title: RegPkg 유틸리티 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- regpkg, registration utility
- registration, regpkg utility
ms.assetid: 1683ee18-59d1-4bab-a674-dd00dd960de3
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: bc1e818e576c4593eb890f1f31b4d67d4c7c4488
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "54979428"
---
# <a name="regpkg-utility"></a>RegPkg 유틸리티
> [!NOTE]
>  Visual Studio에서 패키지를 등록 하려면.pkgdef 파일을 사용 하 여는 것이 좋습니다. 이 VSIX 배포에 대 한 요구 사항인 시스템 레지스트리에 액세스 하지 않고도 확장 배포에 대 한 수 있습니다. Pkgdef 파일을 사용 하 여 만들어진 합니다 [CreatePkgDef 유틸리티](../../extensibility/internals/createpkgdef-utility.md)합니다. Visual Studio 패키지 배포에 대 한 자세한 내용은 참조 하세요. [Visual Studio 확장 전달](../../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 RegPkg.exe 유틸리티를 사용 하 여 VSPackage 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 배포 하도록 준비 합니다. 이 유틸리티는 VSPackage 개발 하는 동안 백그라운드에서 사용 됩니다. 빌드하고 실험적 하이브에서 VSPackage를 실행할 수 있도록 빌드 프로세스의 일부로 실행 됩니다.  
  
 RegPkg 여러 가지 형식으로 시스템 레지스트리 스크립트를 생성할 수 있습니다. .Msi 프로젝트 또는 Windows Installer XML 도구 집합 파일과 같은 배포 프로젝트에서 이러한 스크립트를 통합할 수 있습니다.  
  
 RegPkg.exe에 일반적으로 위치한 \< *Visual Studio SDK 설치 경로*> \VisualStudioIntegration\Tools\Bin\RegPkg.exe 합니다. RegPkg이이 구문은 다음과 같습니다.  
  
```  
RegPkg [/root:<root>] [/regfile:<regfile>] [/rgsfile:<rgsfile> [/rgm]] [/vrgfile:<vrgfile>] [/codebase | /assembly] [/unregister] AssemblyPath  
```  
  
 /root:root  
 지정 된 등록을 수행합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 루트입니다.  
  
 /regfile:FileName  
 레지스트리를 업데이트 하는 것이 아니라.reg 파일을 만듭니다.  /Vrgfile 또는 /rgsfile /wixfile를 사용 하 여 사용할 수 없습니다.  
  
 /rgsfile:FileName  
 레지스트리를 업데이트 하는 것이 아니라.rgs 파일을 만듭니다.  /Regfile /vrgfile 또는 /wixfile를 사용 하 여 사용할 수 없습니다.  
  
 /vrgfile:FileName  
 레지스트리를 업데이트 하는 것이 아니라.vrg 파일을 만듭니다.  /Regfile 또는 /rgsfile /wixfile를 사용 하 여 사용할 수 없습니다.  
  
 /rgm  
 Rgs 파일 외에도.rgm 파일을 만듭니다.  /Rgsfile와 결합 되어야 합니다.  
  
 /wixfile:FileName  
 레지스트리를 업데이트 하는 것이 아니라 Windows Installer XML 도구 집합 호환 파일을 만듭니다.  /Regfile 또는 /rgsfile /vrgfile를 사용 하 여 사용할 수 없습니다.  
  
 /codebase  
 어셈블리 보다는 코드 베이스를 사용 하 여 강제로 등록 합니다.  
  
 /assembly  
 코드 베이스를 사용 하지 않고 어셈블리를 사용 하 여 강제로 등록 합니다.  
  
 /unregister  
 이 패키지를 등록 취소합니다.  사용할 수 없습니다.  
  
 /regfile 또는 /vrgfile 또는 /rgsfile 또는 /wixfile 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSPackage](../../extensibility/internals/vspackages.md)  
 [RegPkg 패키지 등록 문제 해결](../../extensibility/internals/troubleshooting-regpkg-package-registration.md)
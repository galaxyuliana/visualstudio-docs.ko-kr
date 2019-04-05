---
title: '방법: VSIX 패키지에 종속성을 추가 합니다. | Microsoft Docs'
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- package reference
- package assembly
- package dll
- vsix reference
ms.assetid: 8f20177b-dab9-43a3-b959-81a591b451d6
caps.latest.revision: 13
ms.author: gregvanl
manager: jillfra
ms.openlocfilehash: 97118134106614e1e04cd2bc328ad31480618116
ms.sourcegitcommit: 8b538eea125241e9d6d8b7297b72a66faa9a4a47
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/23/2019
ms.locfileid: "58980587"
---
# <a name="how-to-add-a-dependency-to-a-vsix-package"></a>방법: VSIX 패키지에 종속성 추가
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이미 대상 컴퓨터에 존재 하지 않는 모든 종속성을 설치 하는 VSIX 패키지 배포를 설정할 수 있습니다. 이를 위해 VSIX 종속성 source.extension.vsixmanifest 파일을 포함 합니다.  
  
#### <a name="to-add-a-dependency"></a>종속성을 추가 하려면  
  
1.  source.extension.vsixmanifest 파일을 엽니다는 **디자인** 보기. 로 이동 합니다 **종속성** 탭을 클릭 **새로 만들기**합니다.  
  
2.  설치 된 확장을 추가 하:에 **새 종속성 추가** 대화 상자에서 **확장을 설치** 를 선택한 후는 **이름**, 목록에서 확장을 선택 합니다.  
  
3.  설치 되지 않은 다른 VSIX를 추가 하려면::에 **새 종속성 추가** 대화 상자에서 **파일 시스템에 파일** 사용 하 여는 **찾아보기** VSIX를 선택 하려면 단추입니다.  
  
## <a name="see-also"></a>참고 항목  
 [VSIX 확장 스키마 1.0 참조](http://msdn.microsoft.com/76e410ec-b1fb-4652-ac98-4a4c52e09a2b)   
 [VSIX 패키지 분석](../extensibility/anatomy-of-a-vsix-package.md)   
 [Windows Installer 배포에 대한 확장 준비](../extensibility/preparing-extensions-for-windows-installer-deployment.md)

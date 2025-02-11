---
title: 파일에서 바꾸기 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: conceptual
f1_keywords:
- vs.findreplace.replaceinfiles
- vs.replaceinfiles
helpviewer_keywords:
- text searches, replacing text
- Find and Replace window, Replace in Files tab
- Replace in Files tab, Find and Replace window
ms.assetid: ca361466-53bd-44db-a28a-3a74bc03b028
caps.latest.revision: 33
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 72a20b0271542dd914aeb592dda3f0cb446a0000
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65698679"
---
# <a name="replace-in-files"></a>파일에서 바꾸기
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

파일**에서 바꾸기를 사용하여 지정된 파일 집합의 코드에서 문자열 또는 식을 검색하고 찾은 일부 또는 전체 일치 항목을 변경합니다. 찾은 일치 항목과 수행된 작업이 **결과 옵션**에서 선택된 **결과 찾기** 창에 나열됩니다.  
  
> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 도구 메뉴에서 설정 가져오기 및 내보내기를 선택합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
 다음 방법 중 하나를 사용하여 **찾기 및 바꾸기** 창에서 **파일에서 바꾸기**를 표시할 수 있습니다.  
  
### <a name="to-display-replace-in-files"></a>파일에서 바꾸기를 표시하려면  
  
1. **편집** 메뉴에서 **찾기 및 바꾸기**를 확장합니다.  
  
2. **파일에서 바꾸기**를 선택합니다.  
  
     — 또는 —  
  
     **찾기 및 바꾸기** 창이 열려 있으면 도구 모음에서 **파일에서 바꾸기**를 선택합니다.  
  
## <a name="find-what"></a>찾을 내용  
 새 텍스트 문자열이나 식을 검색하려면 상자에 지정합니다. 가장 최근에 검색한 20개 문자열 중 하나를 검색하려면 목록을 열고 검색하려는 문자열을 선택합니다. 검색 문자열에 하나 이상의 정규식을 사용하려는 경우 인접한 **식 작성기** 단추를 선택합니다. 자세한 내용은 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)을 참조하세요.  
  
## <a name="replace-with"></a>바꿀 내용  
 **찾을 내용** 상자에서 문자열의 인스턴스를 다른 문자열로 바꾸려면 **바꿀 내용** 상자에 대체 문자열을 입력합니다. **찾을 내용** 상자에서 문자열의 인스턴스를 삭제하려면 이 필드를 비워 둡니다. 목록을 열면 가장 최근에 검색한 20개의 문자열이 표시됩니다. 대체 문자열에 하나 이상의 정규식을 사용하려는 경우 인접한 **식 작성기** 단추를 선택합니다. 자세한 내용은 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)을 참조하세요.  
  
## <a name="look-in"></a>찾는 위치  
 **찾는 위치** 드롭다운 목록에서 선택한 옵션은 **파일에서 바꾸기**가 현재 활성 파일에서만 검색하는지 또는 특정 폴더 내에 저장된 모든 파일을 검색하는지를 결정합니다. 목록에서 검색 범위를 선택하거나, 폴더 경로를 입력하거나, **찾아보기(...)** 단추를 클릭하여 **검색 폴더 선택** 대화 상자를 표시하고 검색할 폴더 집합을 선택합니다. **찾는 위치** 상자에 경로를 직접 입력할 수도 있습니다.  
  
> [!NOTE]
> 선택한 **찾는 위치** 옵션으로 인해 소스 코드 제어에서 체크 아웃한 파일이 검색되는 경우 로컬 컴퓨터에 다운로드된 파일 버전만 검색됩니다.  
  
## <a name="find-options"></a>찾기 옵션  
 **찾기 옵션** 섹션을 확장하거나 축소할 수 있습니다. 다음 옵션을 선택하거나 선택 취소할 수 있습니다.  
  
 대/소문자 구분  
 이 옵션을 선택하면 **찾기 결과** 창에는 콘텐츠 및 사례와 둘 다 일치하는 **찾을 내용** 문자열의 인스턴스만 표시됩니다. 예를 들어 **대/소문자 구분**을 선택하고 “MyObject”를 검색하면 ”myobject” 또는 “MYOBJECT”가 아닌 “MyObject”가 반환됩니다.  
  
 단어 단위로  
 이 옵션을 선택하면 **찾기 결과** 창에는 전체 단어와 일치하는 **찾을 내용** 문자열의 인스턴스만 표시됩니다. 예를 들어 “MyObject”를 검색하면 “CMyObject” 또는 “MyObjectC”가 아닌 “MyObject”가 반환됩니다.  
  
 정규식 사용  
 이 확인란을 선택하면 특수 표기법을 사용하여 **찾을 내용** 또는 **바꿀 내용** 텍스트 상자에서 텍스트 패턴을 정의할 수 있습니다. 이러한 표기법 목록은 [Visual Studio에서 정규식 사용](../ide/using-regular-expressions-in-visual-studio.md)을 참조하세요.  
  
 이 파일 형식 보기  
 이 목록은 **찾는 위치** 디렉터리에서 검색할 파일 형식을 나타냅니다. 이 필드를 비워 두면 **찾는 위치** 디렉터리의 모든 파일이 검색됩니다.  
  
 목록에서 항목을 선택하여 이러한 특정 형식의 파일을 찾을 미리 구성된 검색 문자열을 입력합니다.  
  
## <a name="result-options"></a>결과 옵션  
 **결과 옵션** 섹션을 확장하거나 축소할 수 있습니다. 다음 옵션을 선택하거나 선택 취소할 수 있습니다.  
  
 찾기 결과 1 창  
 이 옵션을 선택하면 현재 검색 결과로 **찾기 결과 1** 창 내용이 바뀝니다. 이 창은 자동으로 열려 검색 결과를 표시합니다. 이 창을 수동으로 열려면 **보기** 메뉴에서 **다른 창**을 선택하고 **찾기 결과 1**을 선택합니다.  
  
 찾기 결과 2 창  
 이 옵션을 선택하면 현재 검색 결과로 **찾기 결과 2** 창 내용이 바뀝니다. 이 창은 자동으로 열려 검색 결과를 표시합니다. 이 창을 수동으로 열려면 **보기** 메뉴에서 **다른 창**을 선택하고 **찾기 결과 2**를 선택합니다.  
  
 파일 이름만 표시  
 이 확인란을 선택하면 찾기 결과 창에 검색 문자열이 포함된 모든 파일의 전체 이름 및 경로가 나열됩니다. 하지만 문자열이 나타나는 코드 줄은 결과에 포함되지 않습니다. 이 확인란은 파일에서 찾기에만 사용할 수 있습니다.  
  
 모두 바꾸기 이후 수정된 파일 열어 두기  
 이 옵션을 선택하면 바꾸기를 수행한 모든 파일이 열려 있으므로 변경 내용을 실행 취소하거나 저장할 수 있습니다. 메모리 제약 조건은 바꾸기 작업 후에 열려 있을 수 있는 파일 수를 제한할 수 있습니다.  
  
> [!CAUTION]
> 편집을 위해 열려 있는 파일에서만 **실행 취소**를 사용할 수 있습니다. 이 옵션을 선택하지 않으면 편집을 위해 열려 있지 않던 파일은 닫혀 있고 **실행 취소** 옵션을 해당 파일에서 사용할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [텍스트 찾기 및 바꾸기](../ide/finding-and-replacing-text.md)   
 [파일에서 찾기](../ide/find-in-files.md)   
 [Visual Studio 명령](../ide/reference/visual-studio-commands.md)

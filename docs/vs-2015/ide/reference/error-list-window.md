---
title: 오류 목록 창 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-general
ms.topic: reference
f1_keywords:
- VS.ErrorList
helpviewer_keywords:
- Task List
- build errors
- Error List window
- errors [Visual Studio], Error List window
ms.assetid: b7f6d45a-733b-4ad8-bc2f-737a37509e56
caps.latest.revision: 36
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 1d481bbc71019639588c793fee64acd34d5739e8
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680144"
---
# <a name="error-list-window"></a>오류 목록 창
[!INCLUDE[vs2017banner](../../includes/vs2017banner.md)]

참고]
> 오류 목록에는 특정 오류 메시지에 대한 정보가 표시됩니다. 출력 창에서 오류 번호 또는 오류 문자열 텍스트를 복사할 수 있습니다. 출력 창을 표시하려면 Ctrl+Alt+O 키를 누릅니다. [출력 창](../../ide/reference/output-window.md)을 참조하세요.  
  
 **오류 목록** 창을 사용하여 앱을 더 빠르게 개발할 수 있습니다. 예를 들어, 아래와 같은 작업을 수행할 수 있습니다.  
  
- 코드를 작성하는 동안 생성된 오류, 경고 및 메시지를 표시합니다.  
  
- IntelliSense에 감지된 구문 오류를 찾습니다.  
  
- 배포 오류, 특정 정적 분석 오류 및 엔터프라이즈 템플릿 정책을 적용하는 동안 발견된 오류를 찾습니다.  
  
- 오류 메시지 항목을 두 번 클릭하여 문제가 발생한 파일을 열고 오류 위치로 이동합니다.  
  
- 표시되는 항목 및 각 항목에 대해 표시되는 정보 열을 필터링합니다.  
  
- 특정 용어를 검색하고 검색 범위를 현재 프로젝트 또는 문서로 지정합니다.  
  
  **오류 목록**을 표시하려면 **보기/오류 목록** 또는 **Ctrl+\\+E**를 클릭합니다.  
  
  **오류**, **경고** 및 **메시지** 탭을 선택하면 다른 수준의 정보를 볼 수 있습니다.  
  
  목록을 정렬하려면 열 머리글을 클릭합니다. 추가 열을 기준으로 다시 정렬하려면 Shift 키를 누른 상태에서 다른 열 머리글을 클릭합니다. 표시할 열과 숨길 열을 선택하려면 바로 가기 메뉴에서 **열 표시**를 선택합니다. 열이 표시되는 순서를 변경하려면 열 머리글을 왼쪽이나 오른쪽으로 끕니다.  
  
> [!NOTE]
> 표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 여기서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구/설정 가져오기 및 내보내기**를 클릭합니다. 자세한 내용은 [Visual Studio에서 개발 설정 사용자 지정](https://msdn.microsoft.com/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하세요.  
  
## <a name="error-list-filters"></a>오류 목록 필터  
 드롭다운 상자에는 두 가지 형식의 필터가 있습니다. 하나는 도구 모음 오른쪽에 있고 다른 하나는 도구 모음 왼쪽에 있습니다. 도구 모음의 왼쪽에 있는 드롭다운 목록은 사용할 코드 파일의 집합을 지정합니다(**전체 솔루션**, **열린 문서**, **현재 프로젝트**, **현재 문서**).  
  
 검색 범위를 제한하여 오류 그룹을 분석하고 오류 그룹에 대해 작업을 수행할 수 있습니다. 예를 들어, 프로젝트가 컴파일되지 않는 핵심 오류에 집중할 수 있습니다. 다음과 같은 범위 지정 옵션을 사용할 수 있습니다.  
  
1. **열린 문서**: 열려 있는 문서에 대한 오류, 경고 및 메시지를 표시합니다.  
  
2. **현재 프로젝트**: **편집기**에서 현재 선택한 문서의 프로젝트 또는 **솔루션 탐색기**에서 선택한 프로젝트에 대한 오류, 경고 및 메시지를 표시합니다.  
  
   > [!NOTE]
   > 현재 선택한 문서의 프로젝트가 **솔루션 탐색기**에서 선택한 프로젝트와 다른 경우 필터링된 오류, 경고 및 메시지 목록이 변경됩니다.  
  
3. **현재 문서**: **편집기** 또는 **솔루션 탐색기**에서 현재 선택한 문서에 대한 오류, 경고 및 메시지를 표시합니다.  
  
   필터가 검색 결과에 현재 적용되어 있는 경우 **오류 목록** 제목 표시줄에 필터 이름이 나타납니다. 이 경우 **오류**, **경고** 및 **메시지** 단추에 총 항목 수와 함께 필터링된 항목 수가 표시됩니다. 예를 들어, 단추에 x/y개 오류가 표시됩니다. 필터가 적용되지 않은 경우 제목 표시줄에 “오류 목록”만 표시됩니다.  
  
   도구 모음의 오른쪽에 있는 목록은 빌드의 오류(빌드 작업으로 인한 오류) 또는 IntelliSense의 오류(빌드 실행 전 감지된 오류)인지 또는 둘 다인지 지정합니다.  
  
## <a name="search"></a>검색  
 **오류 목록** 도구 모음의 오른쪽에 있는 **오류 목록 검색** 텍스트 상자를 사용하여 오류 목록에서 특정 오류를 찾습니다. 오류 목록에 표시되는 모든 열을 검색할 수 있으며 검색 결과는 항상 쿼리나 적용된 필터 대신 정렬 우선 순위가 있는 열을 기준으로 정렬됩니다. **오류 목록**에 포커스가 있는 동안 **Esc** 키를 선택하면 검색어와 필터링된 검색 결과를 지울 수 있습니다. 텍스트 상자의 오른쪽에 있는 **X**를 클릭해서도 지울 수 있습니다.  
  
## <a name="save"></a>저장  
 오류 목록을 복사하고 파일에 저장할 수 있습니다. 복사하려는 오류를 선택하고 선택 항목을 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **복사**를 선택합니다. 그런 다음 오류를 파일에 붙여 넣을 수 있습니다. 오류를 Excel 스프레드시트에 붙여 넣으면 필드가 다른 열로 나타납니다.  
  
## <a name="ui-element-list"></a>UI 요소 목록  
 심각도  
 여러 종류의 **오류 목록** 항목을 표시합니다(**오류**, **메시지**, **경고**, **경고(활성)**, **경고(비활성)**).  
  
 코드  
 오류 코드를 표시합니다.  
  
 설명  
 항목의 텍스트를 표시합니다.  
  
 프로젝트  
 현재 프로젝트의 이름을 표시합니다.  
  
 파일  
 파일 이름을 표시합니다.  
  
 줄  
 문제가 발생한 줄을 표시합니다.

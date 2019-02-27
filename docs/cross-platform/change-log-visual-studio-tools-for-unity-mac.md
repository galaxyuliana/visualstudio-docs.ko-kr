---
title: 변경 로그(Visual Studio Tools for Unity, Mac) | Microsoft Docs
ms.custom: ''
ms.date: 11/13/2018
ms.technology: vs-unity-tools
ms.topic: conceptual
ms.assetid: 33a6ac54-d997-4308-b5a0-af7387460849
author: therealjohn
ms.author: johmil
manager: crdun
ms.workload:
- unity
ms.openlocfilehash: d9563d45d9a09e4402f1586a18fe9e5d7d9775c1
ms.sourcegitcommit: d0425b6b7d4b99e17ca6ac0671282bc718f80910
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/21/2019
ms.locfileid: "56611076"
---
# <a name="change-log-visual-studio-tools-for-unity-mac"></a>변경 로그(Visual Studio Tools for Unity, Mac)
Visual Studio Tools for Unity에 대한 변경 로그입니다.

## <a name="1700"></a>1.7.0.0
 릴리스 날짜: 2018년 11월 13일

### <a name="new-features"></a>새 기능

-   **디버거:**

    -   연결 대화 상자에(IP, 머신 이름) 클라이언트 추가 정보가 추가되었습니다.

### <a name="bug-fixes"></a>버그 수정

-   **디버거:**

     -   특히 ‘Unity에 연결’을 누르거나 게임을 다시 시작할 때, Unity의 디버거 엔진과 통신하는 데 사용되는 라이브러리에서 교착 상태가 발생하여 Visual Studio 또는 Unity를 동결시키는 문제가 해결되었습니다.

-   **통합:**

     -   다른 기본 편집기가 선택되었을 때 고정 Unity 플러그 인 활성화.

     -   고정 Unity 파일 템플릿 생성.

## <a name="1602"></a>1.6.0.2
 릴리스 날짜: 2018년 7월 24일

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

     -   Unity에서 수정된 Unity 성능 버그에 대한 해결 방법이 롤백되었습니다.

## <a name="1601"></a>1.6.0.1
 릴리스 날짜: 2018년 7월 10일

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

     -   셰이더 코드 색 지정 지원이 수정되었습니다.

## <a name="1600"></a>1.6.0.0
 릴리스 날짜: 2018년 6월 26일

### <a name="bug-fixes"></a>버그 수정

-   **마법사:**

    -   OnApplicationFocus 메시지에서 오타가 수정되었습니다.

-   **Project Generation:**

     -   Unity 성능 버그에 대한 일시적인 해결 방법: 프로젝트를 생성할 때 MonoIslands를 캐시합니다.

     -   새 Unity 런타임에서 사용하는 경우 더 이상 이식 가능한 pdb를 mdb로 변환하지 않습니다.

## <a name="1502"></a>1.5.0.2
 릴리스 날짜: 2018년 4월 18일

### <a name="new-features"></a>새 기능

-   **통합:**

    -   기본 셰이더 코드 완성에 대한 지원이 추가되었습니다.

    -   셰이더 파일에서 주석을 설정/해제하는 지원이 추가되었습니다.

## <a name="1501"></a>1.5.0.1
 릴리스 날짜: 2018년 3월 28일

### <a name="new-features"></a>새 기능

-   **통합:**

    -   Unity 프로젝트 탐색기에서 추가 템플릿에 대한 지원이 추가되었습니다.

## <a name="1500"></a>1.5.0.0
 릴리스 날짜: 2018년 3월 21일

### <a name="new-features"></a>새 기능

-   **통합:**

    -   USB로 연결된 Android 플레이어에 연결 및 검색에 대한 지원이 추가되었습니다.

## <a name="1403"></a>1.4.0.3
 릴리스 날짜: 2018년 3월 5일

### <a name="new-features"></a>새 기능

-   **Project Generation:**

    -   Unity 2018.1에서 새 프로젝트 생성기에 대한 지원이 추가되었습니다.

-   **통합:**

    -   전용 설정에 대한 옵션 패널이 추가되었습니다.

## <a name="1402"></a>1.4.0.2
 릴리스 날짜: 2018년 1월 24일

### <a name="bug-fixes"></a>버그 수정

-   **Project Generation:**

    -   Mono 버전 검색이 수정되었습니다.

-   **통합:**

    -   2018.1 및 플러그 인 활성화의 타이밍 문제가 수정되었습니다.

    -   새 플레이어를 검색하는 경우 알림이 수정되었습니다.

## <a name="1401"></a>1.4.0.1
 릴리스 날짜: 2018년 1월 23일

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   두 번 클릭 시 확장/축소 폴더 수정함

## <a name="1400"></a>1.4.0.0
 릴리스 날짜: 2017년 12월 13일

### <a name="new-features"></a>새 기능

-   **Project Generation:**

    -   .NET Standard에 대한 지원이 추가되었습니다.

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   자동 pdb에서 mdb로의 디버그 기호 변환을 수정했습니다.

## <a name="1301"></a>1.3.0.1
 릴리스 날짜: 2017년 12월 12일

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   배열 크기를 변경하는 동안 검사기에 영향을 주는 EditorPrefs.GetBool에 대한 간접 호출이 수정되었습니다.

-   **마법사:**

    -   메서드를 삽입하기 전에 roslyn 컨텍스트를 새로 고칩니다.

## <a name="1300"></a>1.3.0.0
 릴리스 날짜: 2017년 11월 20일

### <a name="new-features"></a>새 기능

-   **마법사:**

    -   "Unity 메시지 구현" 마법사가 추가되었습니다.

    -   Mac 7.4용 VS에서 새 완성 API에 대한 지원이 추가되었습니다.

## <a name="1200"></a>1.2.0.0
 릴리스 날짜: 2017년 10월 23일

### <a name="new-features"></a>새 기능

-   **디버거:**

    -   휴대용 디버그 기호 파일에 대한 지원을 추가했습니다.

### <a name="bug-fixes"></a>버그 수정

-   **Project Generation:**

    -   어셈블리 파일 이름에 잘못 추가된 추가 .dll 확장명을 수정했습니다.

    -   이제 기본값이 'true'이므로 AllowAttachedDebuggingOfEditor Unity 플래그를 강제하지 않습니다.

## <a name="1103"></a>1.1.0.3
 릴리스 날짜: 2017년 10월 23일

### <a name="new-features"></a>새 기능

-   **Project Generation:**

    -   .NET 4.6 프로필에 대한 지원이 추가되었습니다.

## <a name="1102"></a>1.1.0.2
 릴리스 날짜: 2017년 8월 8일

### <a name="new-features"></a>새 기능

-   **디버거:**

    -   어떤 Unity에 연결할지 확실하지 않은 경우 프로세스에 연결 대화 상자를 시작합니다.

-   **Project Generation:**

    -   Unity 5.6을 사용할 경우 안전하지 않은 컴파일 스위치를 항상 사용하도록 설정합니다.

## <a name="1101"></a>1.1.0.1
 릴리스 날짜: 2017년 7월 20일

### <a name="new-features"></a>새 기능

-   **통합:**

    -   지역화된 리소스에 대한 지원이 추가되었습니다.

## <a name="1100"></a>1.1.0.0
 릴리스 날짜: 2017년 7월 12일

### <a name="new-features"></a>새 기능

-   **통합:**

    -   프로세스에 연결 창을 통해 플레이어와 편집기에 연결에 대한 지원이 추가되었습니다.

-   **Project Generation:**

    -   mcs.rsp 파일을 사용한 어셈블리 이름 참조를 수정했습니다.

    -   assembly.json 컴파일 단위 지원이 추가되었습니다.

    -   API 수준을 사용한 정의를 수정했습니다.

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   컴파일할 때 셰이더 오류 메시지를 수정했습니다.

## <a name="1001"></a>1.0.0.1
 릴리스 날짜: 2017년 5월 4일

### <a name="bug-fixes"></a>버그 수정

-   **통합:**

    -   하이브리드 및 일반 프로젝트를 사용하여 활성 문서 추적을 수정했습니다.

## <a name="1000"></a>1.0.0.0
 릴리스 날짜: 2017년 5월 3일

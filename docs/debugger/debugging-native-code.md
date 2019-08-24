---
title: 네이티브 코드 디버깅 | Microsoft Docs
ms.date: 04/11/2017
ms.topic: conceptual
f1_keywords:
- vs.debug
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- debugging native code
- debugging [C++], native code
- debugging [Visual Studio], native code
- native code, debugging
ms.assetid: d94eee90-7e0d-4cac-88c1-9831030daa5e
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- cplusplus
ms.openlocfilehash: 5a7cf0b150c45037941010bf7e611f4bc21252c7
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62851903"
---
# <a name="debugging-native-code"></a>네이티브 코드 디버깅
이 단원에서는 네이티브 애플리케이션의 몇 가지 일반적인 디버깅 문제와 기술에 대해 설명합니다. 이 단원에서 설명하는 기술은 높은 수준의 기술입니다. Visual Studio 디버거를 사용 하는 방법은 참조 하세요 [디버거 소개](../debugger/debugger-feature-tour.md)).

## <a name="in-this-section"></a>섹션 내용
 [방법: 최적화 된 코드를 디버그](../debugger/how-to-debug-optimized-code.md) 프로그램을 디버그 및 릴리스 구성에 대 한 기본 최적화 설정의 최적화 되지 않은 버전을 디버깅 해야 하는 이유 특히, 최적화 된 코드를 디버깅 하는 것에 대 한 팁을 제공 하 고 찾기만 하는 버그에 대 한 팁 (디버그 빌드 구성 최적화 설정) 하는 최적화 된 코드에 표시 합니다.

 [DebugBreak 및 __debugbreak](../debugger/debugbreak-and-debugbreak.md) Win32 설명 `DebugBreak` 함수 및 플랫폼 SDK의 참조 항목에 대 한 링크를 제공 합니다. `__debugbreak` 내장 함수도 설명합니다.

 [C /C++ 어설션을](../debugger/c-cpp-assertions.md) 어설션 문, 작동 방식 (논리 오류 검색, 작업의 결과 확인 하 고 오류 조건 테스트)를 사용의 이점에 설명의 상호 작용 `_DEBUG`, 및 유형의 지 원하는 어설션 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.

 [방법: 인라인 어셈블리 코드 디버그](../debugger/how-to-debug-inline-assembly-code.md) 어셈블리 명령 및 레지스터 창의 보기를 보려는 디스어셈블리 창 사용에 대 한 짧은 지침 레지스터 내용을 제공 하 고 해당 windows에 대 한 항목에 대 한 링크를 제공 합니다.

 [MFC 디버깅 기술](../debugger/mfc-debugging-techniques.md) 디버깅 기술 등의 MFC 프로그램에 대 한 링크가 나와 있습니다: 어설션, MFC, MFC의에서 누수 afxDebugBreak, TRACE 매크로, 메모리를 탐지 및 빌드 MFC 디버그 크기 줄이기.

 [CRT 디버깅 기술](../debugger/crt-debugging-techniques.md) malloc와 _malloc_dbg, 디버그 후크 함수 작성, CRT 디버그 힙 간의 차이점, CRT 디버그 라이브러리 사용, 보고서 매크로 포함 하 여 C 런타임 라이브러리에 대 한 디버깅 기술 한 링크를 제공 합니다.

 [네이티브 코드 Faq 디버깅](../debugger/debugging-native-code-faqs.md) 시각적 개체를 디버깅 하는 방법에 대 한 질문과 대답을 제공 합니다 C++ 프로그램

 [COM 및 ActiveX 디버깅](../debugger/com-and-activex-debugging.md) COM 및 ActiveX 응용 프로그램을 COM에 대 한 사용할 수 있는 도구를 포함 하 여 디버깅 및 ActiveX 디버깅 정보를 제공 합니다.

 [방법: 삽입 된 코드를 디버그](../debugger/how-to-debug-injected-code.md) 특성을 사용 하는 코드를 디버깅에 대 한 지침을 제공 합니다. 여기에는 소스 주석을 표시하는 방법, 삽입한 코드를 보는 방법, 현재 실행 위치에서 디스어셈블리 코드를 보는 방법 등의 내용이 들어 있습니다.

 [연습: 병렬 응용 프로그램을 디버깅](../debugger/walkthrough-debugging-a-parallel-application.md) 를 사용 하는 방법에 설명 합니다 **병렬 작업** 및 **병렬 스택** 병렬 응용 프로그램을 디버깅 하는 windows 도구입니다.

## <a name="related-sections"></a>관련 단원
 [Visual C++ 프로젝트 형식](../debugger/debugging-preparation-visual-cpp-project-types.md) 시각적 개체에서 만든 기본 프로젝트 형식을 디버깅 하는 방법에 설명 하는 항목에 대 한 링크를 제공 합니다. C++ 프로젝트 템플릿.

 [DLL 프로젝트 디버깅](../debugger/debugging-dll-projects.md) 네이티브 및 관리 되는 Dll을 디버깅 하는 방법에 대해 설명 합니다.

 [디버거 소개](../debugger/debugger-feature-tour.md) 의 디버깅 설명서 단원에 대 한 링크를 제공 합니다. 이러한 정보에는 디버거의 새로운 기능, 설정 및 준비, 중단점, 예외 처리, 편집하며 계속하기, 관리 코드 디버깅, 네이티브 코드 디버깅, SQL 디버깅, 사용자 인터페이스 참조 등이 있습니다.

## <a name="see-also"></a>참고 항목

- [디버거 보안](../debugger/debugger-security.md)
- [Visual Studio의 디버깅](../debugger/index.md)
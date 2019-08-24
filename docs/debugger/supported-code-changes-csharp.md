---
title: 코드 변경 내용을 지원 (C# 및 Visual Basic) | Microsoft Docs
ms.date: 10/11/2018
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- Edit and Continue [C#], supported code changes
- Edit and Continue [Visual Basic], supported code changes
ms.assetid: c7a48ea9-5a7f-4328-a9d7-f0e76fac399d
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: f20f61ffc4a6e4105a96b58c3dc73e7154e7c9cd
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62929725"
---
# <a name="supported-code-changes-c-and-visual-basic"></a>코드 변경 내용을 지원 (C# 및 Visual Basic)
편집하며 계속하기에서는 메서드 본문 내의 코드 변경 유형을 대부분 처리합니다. 그러나 메서드 본문 외부의 변경 내용 대부분과 메서드 본문 내의 몇 가지 변경 내용은 디버깅 중에 적용할 수 없습니다. 이러한 지원되지 않는 변경 내용을 적용하려면 디버깅을 중지하고 새로운 버전의 코드로 다시 시작해야 합니다.

## <a name="supported-changes-to-code"></a>지원 되는 코드 변경

아래 테이블에 생성 될 수 있는 변경 내용을 보여 줍니다 C# 및 세션을 다시 시작 하지 않고 디버깅 세션 중에 Visual Basic 코드입니다.

|언어 요소/기능|지원 되는 편집 작업|제한 사항|
|-|-|-|
|유형|메서드, 필드, 생성자, et al 추가|[예](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|
|반복기|추가 또는 수정|아니요|
|async/await 식|추가 또는 수정|[예](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|
|동적 개체|추가 또는 수정|아니요|
|람다 식|추가 또는 수정|[예](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|
|LINQ 식|추가 또는 수정|[람다 식은 동일](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits)|

> [!NOTE]
> 편집 하며 계속 하기에서 일반적으로 문자열 보간 및 null 조건부 연산자와 같은 새로운 언어 기능은 사용할 수 있습니다. 최신 정보를 참조 하세요. 합니다 [Enc 편집 지원](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits) 페이지입니다.

## <a name="unsupported-changes-to-code"></a>코드에 지원 되지 않는 변경
 다음 변경 내용을 적용할 수 없습니다 C# 및 Visual Basic 코드 디버깅 세션 중:

- 현재 문 또는 다른 모든 활성 문에 대한 변경

     활성 문에는 호출 스택의 함수에서 현재 문을 실행하기 위해 호출된 모든 문이 포함됩니다.

     현재 문은 소스 창에서 노란색 배경으로 표시됩니다. 다른 활성 문은 배경이 회색으로 표시되고 읽기 전용입니다. 이러한 기본 색상은 **옵션** 대화 상자에서 변경할 수 있습니다.

- 다음 표에서 언어 요소에서 지원 되지 않는 코드 변경 내용을 보여 줍니다.

|언어 요소/기능|지원 되지 않는 편집 작업|
|-|-|
|모든 코드 요소|이름 바꾸기|
|네임스페이스|Add|
|네임 스페이스, 형식, 멤버|삭제|
|제네릭|추가 또는 수정|
|인터페이스|수정|
|유형|재정의 추상 또는 가상 멤버를 추가 (참조 [세부 정보](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))|
|유형|소멸자 추가|
|멤버|포함된 된 interop 형식 참조 멤버를 수정 합니다.|
|멤버 (Visual Basic)|On Error 또는 Resume 문 사용 하 여 멤버를 수정 합니다.|
|멤버 (Visual Basic)|집계, 그룹화, 간단한 조인 또는 그룹 조인 LINQ 쿼리 절이 포함 된 멤버를 수정 합니다.|
|메서드|서명을 수정 합니다.|
|메서드|추상 메서드가 될 추상이 아닌 메서드 본문을 추가 하 여 확인|
|메서드|메서드 본문을 삭제 합니다.|
|특성|추가 또는 수정|
|이벤트 또는 속성|수정 형식 매개 변수, 기본 형식, 대리자, 형식 또는 반환 형식 |
|연산자 또는 인덱서|수정 형식 매개 변수, 기본 형식, 대리자, 형식 또는 반환 형식 |
|catch 블록|활성 문을 포함 하는 경우 수정|
|try – catch – finally 블록|활성 문을 포함 하는 경우 수정|
|using 문|Add|
|비동기 메서드/람다|.NET Framework 4를 대상으로 하는 프로젝트에서 비동기 메서드/람다를 수정 하 고 낮은 (참조 [세부 정보](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))|
|반복기|.NET Framework 4를 대상으로 하는 프로젝트에서 반복기를 수정 하 고 낮은 (참조 [세부 정보](https://github.com/dotnet/roslyn/wiki/EnC-Supported-Edits))|

## <a name="unsafe-code"></a>안전하지 않은 코드
 안전하지 않은 코드에 대한 변경에는 안전한 코드에 대한 변경과 동일한 제한 사항이 적용되고 한 가지 제한 사항이 추가로 적용됩니다. 편집 하며 계속 하기 변경 내용이 포함 된 메서드 안에 있는 안전 하지 않은 코드를 지원 하지 않습니다는 `stackalloc` 연산자입니다.

## <a name="unsupported-app-scenarios"></a>지원 되지 않는 앱 시나리오

지원 되지 않는 앱 및 플랫폼에는 ASP.NET 5, Silverlight 5 및 Windows 8.1 포함 됩니다.

> [!NOTE]
> 지원 되는 앱에서 Windows 10 및.NET Framework 4.6을 대상으로 하는 x86 및 x64 앱 UWP 포함 데스크톱 또는 이후 버전 (.NET Framework는 데스크톱 버전에만 해당).

## <a name="unsupported-scenarios"></a>지원되지 않는 시나리오
 다음과 같은 디버깅 시나리오에서는 편집하며 계속하기를 사용할 수 없습니다.

- 혼합 모드(네이티브/관리) 디버깅

- SQL 디버깅

- Dr. Watson 덤프 디버깅

- 포함된 런타임 애플리케이션 디버깅

- 응용 프로그램 디버깅 프로세스에 연결 (**디버그 > 프로세스에 연결**)를 선택 하 여 응용 프로그램을 실행 하는 대신 **시작** 에서 합니다 **디버그** 메뉴.

- 최적화된 코드 디버깅

- 빌드 오류가 발생하여 새 버전을 빌드하는 데 실패한 후 이전 버전의 코드 디버깅

## <a name="see-also"></a>참고 항목
- [편집하며 계속하기(Visual C#)](../debugger/edit-and-continue-visual-csharp.md)
- [방법: 편집하며 계속하기 사용(C#)](../debugger/how-to-use-edit-and-continue-csharp.md)
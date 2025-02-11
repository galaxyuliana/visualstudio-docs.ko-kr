---
title: C++정적 코드 분석 스토어 앱
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-test
ms.topic: conceptual
f1_keywords:
- vs.codeanalysis.propertypages.native.express
ms.assetid: c5355e43-a37c-4686-a969-18e3dfc59a9c
caps.latest.revision: 15
author: alexhomer1
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 799e75dff8202ef041399cc6e0fcfb791dc7e868
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65686529"
---
# <a name="analyze-c-code-quality-of-store-apps-using-visual-studio-static-code-analysis"></a>Visual Studio 정적 코드 분석을 사용하여 스토어 앱의 C++ 코드 품질 분석
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Windows 및 Windows Phone 적용 됩니다] (.. /Image/windows_and_phone_content.png "windows_and_phone_content")

 Visual Studio Express 버전의 코드 분석 도구는 코드에 일련의 일반적인 문제 및 바람직한 프로그래밍 관행의 위반 사항이 있는지 검사합니다. 코드 분석은 유효하지만 해당 코드를 사용하는 당사자나 다른 사용자에게 계속 문제를 일으킬 수 있는 특정 코드 패턴을 검색하므로, 코드 분석 경고는 컴파일러 오류 및 경고와 다릅니다. 코드 분석 시 테스트를 통해 검색하기 힘든 코드 오류도 찾을 수 있습니다. 개발 프로세스에서 코드 분석 도구를 정기적으로 실행하면 완성된 응용 프로그램의 품질을 향상시킬 수 있습니다.

> [!NOTE]
> Visual Studio Ultimate, Visual Studio Premium 및 Visual Studio Professional에서는 코드 분석 도구의 기능을 모두 사용할 수 있습니다. MSDN 라이브러리의 [코드 분석 도구를 사용하여 애플리케이션 품질 분석](https://msdn.microsoft.com/library/dd264897.aspx)을 참조하세요.

## <a name="BKMK_Run"></a> 코드 분석 실행
 Visual Studio 솔루션에서 코드 문석을 실행하려면 다음을 수행합니다.

- **빌드** 메뉴에서 **솔루션에서 코드 분석 실행**을 선택합니다.

  프로젝트를 빌드할 때마다 자동으로 코드 분석을 실행하려면 다음을 수행합니다.

1. 솔루션 탐색기에서 프로젝트 이름을 선택한 다음 **속성**을 선택합니다.

2. 프로젝트 속성 페이지에서 **코드 분석**을 선택한 다음 **빌드할 때 C/C++에 코드 분석 사용**을 선택합니다.

   솔루션이 컴파일되고 코드 분석이 실행됩니다. 코드 분석 창에 결과가 나타납니다.

   ![코드 분석 창](../test/media/ca-cpp-collapsed.png "CA_CPP_Collapsed")

## <a name="BKMK_Analyze"></a> 코드 분석 경고 분석 및 해결
 특정 경고를 분석하려면 코드 분석 창에서 경고 제목을 선택합니다. 경고가 확장되어 문제에 대한 자세한 정보가 표시됩니다. 가능한 경우 코드 분석에 줄 번호와 경고를 초래한 분석 논리가 표시됩니다.

 ![확장된 코드 분석 경고](../test/media/ca-cpp-expanded-callout.png "CA_CPP_Expanded_Callout")

 경고를 확장하면 Visual Studio Code 편집기에서 경고를 발생시킨 코드 줄이 강조 표시됩니다.

 ![강조 표시된 소스 코드](../test/media/ca-cpp-sourceline.png "CA_CPP_SourceLine")

 문제를 파악한 후 코드에서 해결할 수 있습니다. 그런 다음 코드 분석을 다시 실행하여 코드 분석 창에 더 이상 경고가 나타나지 않는지와 수정으로 인해 새로운 경고가 발생하지 않는지 확인합니다.

> [!TIP]
> 코드 분석 창에서 코드 분석을 다시 실행할 수 있습니다. **분석** 단추를 선택한 다음 분석 범위를 선택합니다. 전체 솔루션 또는 선택한 프로젝트에 대한 분석을 다시 실행할 수 있습니다.

## <a name="BKMK_Suppress"></a> 코드 분석 경고 표시하지 않기
 코드 분석 경고를 수정하지 않도록 결정하는 경우가 있습니다. 경고를 해결하려면 코드의 실제 구현에서 문제가 발생할 가능성과 관련하여 너무 많은 기록이 필요하다고 판단할 수 있습니다. 또는 경고에 사용되는 분석이 특정 컨텍스트에 적절하지 않다고 판단할 수도 있습니다. 코드 분석 창에 개별 경고가 나타나지 않도록 개별 경고를 표시하지 않을 수 있습니다.

 경고를 표시하지 않으려면 다음을 수행합니다.

1. 자세한 정보가 표시되지 않으면 경고 제목을 확장합니다.

2. 경고 아래쪽에서 **작업** 링크를 선택합니다.

3. **메시지 표시 안 함**을 선택한 후 **소스**를 선택합니다.

   메시지를 표시하지 않도록 설정하면 코드 줄에 대한 경고를 표시하지 않는 `#pragma(warning:`*WarningId*`)`가 삽입됩니다.

## <a name="BKMK_Search"></a> 코드 분석 결과 검색 및 필터링
 긴 경고 메시지 목록을 검색하고 다중 프로젝트 솔루션에서 경고를 필터링할 수 있습니다.

 ![코드 분석 검색 및 필터 창](../test/media/ca-searchfilter.png "CA_SearchFilter")

## <a name="Warnings"></a> C++ 코드 분석 경고
 코드 분석 시 C++ 코드에 대해 다음과 같은 경고가 발생합니다.

|                                      규칙                                      |                                                  설명                                                  |
|--------------------------------------------------------------------------------|---------------------------------------------------------------------------------------------------------------|
|                       [C6001](../code-quality/c6001.md)                        |                                          초기화되지 않은 메모리 사용                                           |
|                       [C6011](../code-quality/c6011.md)                        |                                          Null 포인터 역참조                                           |
|                       [C6029](../code-quality/c6029.md)                        |                                            확인되지 않은 값 사용                                             |
|                       [C6053](../code-quality/c6053.md)                        |                                          호출의 0 종료                                           |
|                       [C6059](../code-quality/c6059.md)                        |                                               잘못된 연결                                               |
|                       [C6063](../code-quality/c6063.md)                        |                                  Format 함수에 문자열 인수 없음                                   |
|                       [C6064](../code-quality/c6064.md)                        |                                  Format 함수에 정수 인수 없음                                  |
|                       [C6066](../code-quality/c6066.md)                        |                                  Format 함수에 포인터 인수 없음                                  |
|                       [C6067](../code-quality/c6067.md)                        |                              Format 함수에 문자열 포인터 인수 없음                               |
|                       [C6101](../code-quality/c6101.md)                        |                                        초기화되지 않은 메모리 반환                                         |
|                       [C6200](../code-quality/c6200.md)                        |                                         인덱스가 버퍼 최대값을 초과함                                          |
|                       [C6201](../code-quality/c6201.md)                        |                                      인덱스가 스택 버퍼 최대값을 초과함                                       |
|                       [C6270](../code-quality/c6270.md)                        |                                   Format 함수에 부동 인수 없음                                   |
|                       [C6271](../code-quality/c6271.md)                        |                                       Format 함수의 추가 인수                                       |
|                       [C6272](../code-quality/c6272.md)                        |                                     Format 함수의 비부동 인수                                     |
|                       [C6273](../code-quality/c6273.md)                        |                                    Format 함수에 비정수 인수                                     |
|                       [C6274](../code-quality/c6274.md)                        |                                   Format 함수의 비문자 인수                                   |
|                       [C6276](../code-quality/c6276.md)                        |                                              잘못된 문자열 캐스팅                                              |
|                       [C6277](../code-quality/c6277.md)                        |                                          잘못된 CreateProcess 호출                                           |
|                       [C6284](../code-quality/c6284.md)                        |                                  Format 함수의 개체 인수 잘못됨                                   |
|                       [C6290](../code-quality/c6290.md)                        |                                      논리 부정 비트 AND 우선 순위                                       |
|                       [C6291](../code-quality/c6291.md)                        |                                       논리 부정 비트 OR 우선 순위                                       |
|                       [C6302](../code-quality/c6302.md)                        |                             Format 함수에 대한 잘못된 문자열 인수                              |
|                       [C6303](../code-quality/c6303.md)                        |                           Format 함수에 대한 잘못된 와이드 문자열 인수                           |
|                       [C6305](../code-quality/c6305.md)                        |                                         크기 및 개수 사용 불일치                                         |
|                       [C6306](../code-quality/c6306.md)                        |                                   잘못된 변수 인수 함수 호출                                   |
|                       [C6328](../code-quality/c6328.md)                        |                                       잠재적 인수 형식 불일치                                        |
|                       [C6385](../code-quality/c6385.md)                        |                                                 읽기 오버런                                                  |
|                       [C6386](../code-quality/c6386.md)                        |                                                 쓰기 오버런                                                 |
|                       [C6387](../code-quality/c6387.md)                        |                                            잘못된 매개 변수 값                                            |
|                       [C6500](../code-quality/c6500.md)                        |                                          잘못된 특성 속성                                           |
|                       [C6501](../code-quality/c6501.md)                        |                                     특성 속성 값 충돌                                     |
|                       [C6503](../code-quality/c6503.md)                        |                                           참조는 Null일 수 없음                                           |
|                       [C6504](../code-quality/c6504.md)                        |                                              비포인터에 대한 Null                                              |
|                       [C6505](../code-quality/c6505.md)                        |                                               Void에 대한 MustCheck                                               |
|                       [C6506](../code-quality/c6506.md)                        |                                      비포인터 또는 배열에 대한 버퍼 크기                                      |
| [C6507](https://msdn.microsoft.com/18f88cd1-d035-4403-a6a4-12dd0affcf21)        |                                       역참조 0에서의 Null 불일치                                       |
|                       [C6508](../code-quality/c6508.md)                        |                                           상수에 대한 쓰기 액세스                                            |
|                       [C6509](../code-quality/c6509.md)                        |                                          사전 조건에서 반환이 사용됨                                          |
|                       [C6510](../code-quality/c6510.md)                        |                                        비포인터에 대한 Null 종료                                         |
|                       [C6511](../code-quality/c6511.md)                        |                                          MustCheck는 Yes 또는 No여야 함                                          |
|                       [C6513](../code-quality/c6513.md)                        |                                       버퍼 크기가 없는 요소 크기                                        |
|                       [C6514](../code-quality/c6514.md)                        |                                        버퍼 크기가 배열 크기를 초과함                                         |
|                       [C6515](../code-quality/c6515.md)                        |                                          비포인터에 대한 버퍼 크기                                           |
|                       [C6516](../code-quality/c6516.md)                        |                                          특성에 대한 속성 없음                                           |
|                       [C6517](../code-quality/c6517.md)                        |                                       읽기 불가능 버퍼에 대한 유효 크기                                       |
|                       [C6518](../code-quality/c6518.md)                        |                                     쓰기 불가능 버퍼에 대한 쓰기 가능 크기                                      |
| [C6521](https://msdn.microsoft.com/e98d0ae3-6f13-47b2-9a15-15d4055af9ef)  |                                        잘못된 크기 문자열 역참조                                        |
|                       [C6522](../code-quality/c6522.md)                        |                                           잘못된 크기 문자열 유형                                            |
| [C6523](https://msdn.microsoft.com/11397a31-b224-46b0-afb7-d49ca576a3bb)  |                                         잘못된 크기 문자열 매개 변수                                         |
|                       [C6525](../code-quality/c6525.md)                        |                                   잘못된 크기 문자열 접근할 수 없는 위치                                    |
| [C6526](https://msdn.microsoft.com/59c590c7-0098-4166-a1ac-87f324596002)  |                                        잘못된 크기 문자열 버퍼 유형                                        |
|                       [C6527](../code-quality/c6527.md)                        |              주석이 잘못 되었습니다. 'NeedsRelease ' 속성은 void 형식의 값에 사용할 수 없습니다.               |
|                       [C6530](../code-quality/c6530.md)                        |                                       인식할 수 없는 형식 문자열 스타일                                        |
|                       [C6540](../code-quality/c6540.md)                        | 이 함수에 특성 주석을 사용하면 기존의 모든 __declspec 주석이 무효화됩니다.  |
|                       [C6551](../code-quality/c6551.md)                        |                              크기 사양이 잘못되었습니다. 식을 구문 분석할 수 없습니다.                              |
|                       [C6552](../code-quality/c6552.md)                        |                              Deref= 또는 Notref=가 잘못되었습니다. 식을 구문 분석할 수 없습니다.                               |
|                       [C6701](../code-quality/c6701.md)                        |                                  값이 올바른 Yes/No/Maybe 값이 아닙니다                                  |
|                       [C6702](../code-quality/c6702.md)                        |                                        값이 문자열 값이 아닙니다.                                        |
|                       [C6703](../code-quality/c6703.md)                        |                                           값이 숫자가 아닙니다.                                           |
|                       [C6704](../code-quality/c6704.md)                        |                                    예기치 않은 주석 식 오류가 발생했습니다.                                     |
|                       [C6705](../code-quality/c6705.md)                        |     필요한 주석 인수 개수가 실제 주석 인수 개수와 일치하지 않습니다.      |
|                       [C6706](../code-quality/c6706.md)                        |                                  예기치 않은 주석 오류가 발생했습니다.                                   |
|                      [C28021](../code-quality/c28021.md)                       |                                주석이 달린 매개 변수는 포인터여야 합니다.                                |
|                      [C28182](../code-quality/c28182.md)                       |         NULL 포인터를 역참조하고 있습니다. 포인터에 다른 포인터와 동일한 NULL 값이 포함되어 있습니다.          |
|                      [C28202](../code-quality/c28202.md)                       |                                    비정적 멤버에 대한 잘못된 참조입니다.                                     |
|                      [C28203](../code-quality/c28203.md)                       |                                     클래스 멤버에 대한 모호한 참조입니다.                                      |
|                      [C28205](../code-quality/c28205.md)                       |                           \_Success\_ 또는 \_On_failure\_가 잘못된 컨텍스트에서 사용되었습니다.                            |
|                      [C28206](../code-quality/c28206.md)                       |                                   왼쪽 피연산자가 구조체를 가리킵니다. '->'를 사용하세요.                                   |
|                      [C28207](../code-quality/c28207.md)                       |                                       왼쪽 피연산자가 구조체입니다. '.'를 사용하세요.                                       |
|                      [C28210](../code-quality/c28210.md)                       |                 __on_failure 컨텍스트에 대한 주석이 명시적 사전 컨텍스트에 없어야 합니다.                  |
|                      [C28211](../code-quality/c28211.md)                       |                                 SAL_context에 대해 정적 컨텍스트 이름이 필요합니다.                                  |
|                      [C28212](../code-quality/c28212.md)                       |                                  주석에 대한 포인터 식이 있어야 합니다.                                   |
|                      [C28213](../code-quality/c28213.md)                       | 이전 선언을 수정하지 않고 참조하려면 \_Use_decl_annotations\_ 주석을 사용해야 합니다. |
|                      [C28214](../code-quality/c28214.md)                       |                                   특성 매개 변수 이름은 p1...p9여야 합니다.                                   |
|                      [C28215](../code-quality/c28215.md)                       |                    typefix는 이미 typefix가 있는 매개 변수에 적용할 수 없습니다.                    |
|                      [C28216](../code-quality/c28216.md)                       |        checkReturn 주석은 특정 함수 매개 변수에 대한 사전 조건에만 적용됩니다.         |
|                      [C28217](../code-quality/c28217.md)                       |            함수의 경우 주석에 대한 매개 변수 개수가 파일에 있는 개수와 일치하지 않습니다.             |
|                      [C28218](../code-quality/c28218.md)                       |             함수 매개 변수의 경우 주석의 매개 변수 일치 하지 않는 파일              |
|                      [C28219](../code-quality/c28219.md)                       |                 주석에 있는 매개 변수 주석에 열거의 멤버가 필요합니다.                 |
|                      [C28220](../code-quality/c28220.md)                       |                  주석에 있는 매개 변수에 정수 식이 필요합니다.                   |
|                      [C28221](../code-quality/c28221.md)                       |                        주석에 있는 매개 변수에 문자열 식이 필요합니다.                         |
|                      [C28222](../code-quality/c28222.md)                       |                               주석에 __yes, \__no 또는 \__maybe가 필요합니다.                               |
|                      [C28223](../code-quality/c28223.md)                       |                       주석, 매개 변수에 필요한 토큰/식별자를 찾지 못했습니다.                        |
|                      [C28224](../code-quality/c28224.md)                       |                                        주석에 매개 변수가 필요합니다.                                         |
|                      [C28225](../code-quality/c28225.md)                       |                     주석에서 올바른 필수 매개 변수의 개수를 찾지 못했습니다.                      |
|                      [C28226](../code-quality/c28226.md)                       |                          또한 주석은 현재 선언에서 PrimOp일 수 없습니다.                          |
|                      [C28227](../code-quality/c28227.md)                       |                          또한 주석은 PrimOp일 수 없습니다(이전 선언 참조).                           |
|                      [C28228](../code-quality/c28228.md)                       |                             주석 매개 변수: 주석에서 형식을 사용할 수 없습니다.                              |
|                      [C28229](../code-quality/c28229.md)                       |                                    주석에서 매개 변수를 지원하지 않습니다.                                     |
|                      [C28230](../code-quality/c28230.md)                       |                                     매개 변수 형식에 멤버가 없습니다.                                      |
|                      [C28231](../code-quality/c28231.md)                       |                                       주석은 배열에서만 유효합니다.                                       |
|                      [C28232](../code-quality/c28232.md)                       |                               pre, post 또는 deref가 주석에 적용되지 않았습니다.                               |
|                      [C28233](../code-quality/c28233.md)                       |                                    pre, post 또는 deref가 블록에 적용되었습니다.                                     |
|                      [C28234](../code-quality/c28234.md)                       |                              __at 식이 현재 함수에 적용되지 않습니다.                               |
|                      [C28235](../code-quality/c28235.md)                       |                               함수를 단독으로 주석으로 사용할 수 없습니다.                                |
|                      [C28236](../code-quality/c28236.md)                       |                                함수를 식에 사용할 수 없습니다.                                 |
|                      [C28237](../code-quality/c28237.md)                       |                              매개 변수에 대한 주석이 더 이상 지원되지 않습니다.                               |
|                      [C28238](../code-quality/c28238.md)                       |      매개 변수에 대한 주석에 value, stringValue 및 longValue 중 두 개 이상이 있습니다. paramn=xxx를 사용하세요.       |
|                      [C28239](../code-quality/c28239.md)                       |  매개 변수에 대한 주석에 value, stringValue 또는 longValue와 paramn=xxx가 모두 있습니다. paramn=xxx만 사용하세요.   |
|                      [C28240](../code-quality/c28240.md)                       |                             매개 변수에 대한 주석에 param1이 아니라 param2가 있습니다.                              |
|                      [C28241](../code-quality/c28241.md)                       |                          매개 변수에 대한 함수 주석이 인식되지 않습니다.                           |
|                      [C28243](../code-quality/c28243.md)                       |   매개 변수에 대한 함수 주석에 실제 형식 주석이 허용하는 것보다 많은 역참조가 필요합니다.   |
|                      [C28245](../code-quality/c28245.md)                       |                     함수에 대한 주석에서 멤버가 아닌 함수에 'this'를 주석으로 답니다.                     |
|                      [C28246](../code-quality/c28246.md)                       |                함수의 매개 변수 주석이 매개 변수 형식과 일치하지 않습니다.                 |
|                      [C28250](../code-quality/c28250.md)                       |                    함수에 대한 주석이 일치하지 않습니다. 이전 인스턴스에 오류가 있습니다.                     |
|                      [C28251](../code-quality/c28251.md)                       |                       함수에 대한 주석이 일치하지 않습니다. 이 인스턴스에 오류가 있습니다.                       |
|                      [C28252](../code-quality/c28252.md)                       |           함수에 대한 주석이 일치하지 않습니다. 이 인스턴스에 대한 다른 주석이 매개 변수에 있습니다.           |
|                      [C28253](../code-quality/c28253.md)                       |           함수에 대한 주석이 일치하지 않습니다. 이 인스턴스에 대한 다른 주석이 매개 변수에 있습니다.           |
|                      [C28254](../code-quality/c28254.md)                       |                               dynamic_cast<>()는 주석에서 지원되지 않습니다.                                |
|                      [C28262](../code-quality/c28262.md)                       |                    주석에 대한 주석 구문 오류가 함수에 있습니다.                     |
|                      [C28263](../code-quality/c28263.md)                       |                 내장 주석에 대한 조건부 주석에 구문 오류가 있습니다.                 |
|                      [C28267](../code-quality/c28267.md)                       |                    함수 주석에서 주석 구문 오류가 발견되었습니다.                    |
|                      [C28272](../code-quality/c28272.md)                       |      함수, 매개 변수에 대한 주석이 검사 시 함수 선언과 일치하지 않습니다.      |
|                      [C28273](../code-quality/c28273.md)                       |                    함수의 경우 단서가 함수 선언과 일치하지 않습니다.                     |
|                      [C28275](../code-quality/c28275.md)                       |                                   \_Macro_value\_에 대한 매개 변수가 null입니다.                                    |
|                      [C28279](../code-quality/c28279.md)                       |                           기호의 경우 일치하는 'end'가 없는 'begin'이 있습니다.                            |
|                      [C28280](../code-quality/c28280.md)                       |                           기호의 경우 일치하는 'begin'이 없는 'end'가 있습니다.                           |
|                      [C28282](../code-quality/c28282.md)                       |                                    형식 문자열이 사전 조건에 있어야 합니다.                                    |
|                      [C28285](../code-quality/c28285.md)                       |                                    함수의 경우 매개 변수에 구문 오류가 있습니다.                                    |
|                      [C28286](../code-quality/c28286.md)                       |                                    함수의 경우 끝 부분 근처에 구문 오류가 있습니다.                                    |
|                      [C28287](../code-quality/c28287.md)                       |                함수의 경우 \_At\_() 주석에 구문 오류(인식할 수 없는 매개 변수 이름)                |
|                      [C28288](../code-quality/c28288.md)                       |                  함수의 경우 \_At\_() 주석에 구문 오류(잘못된 매개 변수 이름)                   |
|                      [C28289](../code-quality/c28289.md)                       |                함수의 경우: ReadableTo 또는 WritableTo 없는 위한 제한 사양을 매개 변수로                |
|                      [C28290](../code-quality/c28290.md)                       |           함수의 주석에 실제 매개 변수 개수보다 많은 외부 참조가 있습니다.            |
|                      [C28291](../code-quality/c28291.md)                       |                        함수의 경우 역참조 수준 0에서 post null/notnull이 의미가 없습니다.                        |
|                      [C28300](../code-quality/c28300.md)                       |                            연산자에 호환되지 않는 형식의 식 피연산자입니다.                             |
|                      [C28301](../code-quality/c28301.md)                       |                               함수의 첫 번째 선언에 대한 주석이 없습니다.                               |
|                      [C28302](../code-quality/c28302.md)                       |                             주석에 추가 \_Deref\_ 연산자가 있습니다.                              |
|                      [C28303](../code-quality/c28303.md)                       |                           주석에 모호한 \_Deref\_ 연산자가 있습니다.                            |
|                      [C28304](../code-quality/c28304.md)                       |                     토큰에 부적절하게 배치된 \_Notref\_ 연산자가 적용되었습니다.                      |
|                      [C28305](../code-quality/c28305.md)                       |                                토큰을 구문 분석하는 동안 오류가 발생했습니다.                                 |
|                      [C28350](../code-quality/c28350.md)                       |                  주석이 조건부로 적용할 수 없는 상황을 설명합니다.                   |
|                      [C28351](../code-quality/c28351.md)                       |         주석이 동적 값(변수)을 조건에 사용할 수 없는 경우를 설명합니다.          |

---
title: 디버거 사용자 인터페이스 (XSLT) | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 846fdabd-e5c3-4688-9b0d-a93fbeea1b96
caps.latest.revision: 6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: f7ffc67bd1175a84bf5708c613661a169c093dbd
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65697020"
---
# <a name="debugger-user-interface-xslt"></a>디버거 사용자 인터페이스(XSLT)
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

이 항목에서는 디버거 창과 대화 상자에 대해 설명합니다. XSLT 관련 디버깅 동작이 있는 사용자 인터페이스 부분에 대해서만 설명합니다.  
  
 자세한 내용은 참조는 [사용자 인터페이스 참조 디버깅](../debugger/debugging-user-interface-reference.md)합니다.  
  
## <a name="locals-window"></a>지역 창  
 지역 창에는 스타일시트에 정의되어 있는 변수에 대한 정보가 표시됩니다. 지역 창에는 다음 세 개의 정보 열이 있습니다.  
  
 **이름**  
 이 열에는 현재 범위에 있는 모든 지역 변수의 이름이 포함됩니다. 노드 집합에는 트리 컨트롤이 있으며 이 컨트롤을 드릴다운하여 하위 폴더를 볼 수 있습니다.  
  
 **값**  
 이 열에는 각 변수가 포함하는 값이 표시됩니다. 특성, 처리 명령, 주석, 텍스트 및 CData 노드는 노드의 텍스트 값을 표시합니다. 네임스페이스 노드는 네임스페이스 URI를 표시합니다.  
  
 **Type**  
 이 열에 나열 된 각 변수의 데이터 형식을 식별 합니다 **이름을** 열입니다.  
  
 지역 창에는 XSLT 변형 컨텍스트를 추적하는 미리 정의된 컨텍스트 변수도 표시됩니다. 다음 표에서는 XSLT 디버거에서 사용하는 미리 정의된 컨텍스트 변수를 설명합니다.  
  
|이름|설명|  
|----------|-----------------|  
|`last()`|컨텍스트 크기입니다.|  
|`position()`|컨텍스트 크기에 상대적인 컨텍스트 노드의 위치 또는 인덱스 번호입니다.|  
|`self::node()`|컨텍스트 노드의 값입니다.|  
  
 자세한 내용은 [방법: 디버거 컨텍스트 변경](https://msdn.microsoft.com/library/8a69ea63-2ef0-4b4f-9521-cf8ad2e3ec5e)합니다.  
  
## <a name="output-window"></a>출력 창  
 출력 창에는 디버깅하는 동안 발생하는 오류 메시지 또는 보안 예외가 표시됩니다.  
  
 XSLT 디버거는 별도의 창을 사용하여 디버거 출력을 표시합니다. 출력을 표시 하는 데 사용 하 여 동일한 창에는이 **XSL 출력 표시** 명령입니다.  
  
## <a name="task-list"></a>작업 목록  
 작업 목록에는 스타일시트의 모든 컴파일 오류가 나열됩니다. 오류를 두 번 클릭하면 오류가 발생한 줄에 커서가 놓입니다.  
  
 작업 목록에는 XSLT 파일의 스크립트 블록에서 발생한 모든 오류가 포함됩니다.  
  
> [!NOTE]
> XSLT 디버거에는 경고가 없으므로 작업 목록에 절대로 표시되지 않습니다.  
  
## <a name="breakpoints-window"></a>중단점 창  
 중단점 창에는 현재 프로젝트에 설정된 모든 중단점이 표시됩니다. 창이 표시되어 있는 동안 중단점을 추가하면 자동으로 창이 업데이트되어 새 중단점을 표시합니다.  
  
 중단점 창은 다른 Visual Studio 디버거와 같은 방식으로 작동해야 합니다.  
  
## <a name="command-windowimmediate-window"></a>명령 창/직접 실행 창  
 XSLT 디버거의 이번 릴리스에서는 구현되지 않습니다.  
  
## <a name="watch-window"></a>조사식 창  
 조사식 창을 사용하여 변수를 계산합니다. 변수 값을 변경할 수도 있습니다.  
  
 조사식 창에 표시된 변수는 현재 컨텍스트(호출 스택에서 맨 위에 있는 항목)에 대한 변수입니다. 컨텍스트를 변경하면 조사식 창이 업데이트되어 해당 컨텍스트에 대해 설정된 변수를 표시합니다.  
  
## <a name="call-stack-window"></a>호출 스택 창  
 호출 스택 창을 사용하여 호출 스택, 매개 변수 형식 및 매개 변수 값의 함수 이름을 볼 수 있습니다. 디버깅 중인 프로그램이 중단 상태인 경우에만 호출 스택 정보가 표시됩니다.  
  
 호출 스택은 XSLT 실행의 다양한 컨텍스트를 나타냅니다. 예를 들어, "a" 템플릿에서 "b" 템플릿으로 호출이 있는 경우 "a" 템플릿과 "b" 템플릿이 호출 스택 창의 목록 맨 위에 현재 컨텍스트와 함께 나타납니다. 사용자는 현재 실행 중인 쿼리를 볼 수 있습니다.  
  
 XSLT 파일에 템플릿 이름이 없을 경우 XSLT 프로세서에서 생성된 이름이 사용됩니다.  
  
 목록 맨 위에 있는 항목을 제외한 다른 항목을 클릭하면 표준 녹색 강조 표시 및 녹색 화살표를 사용하여 XSLT 실행 분기가 발생한 뷰어가 나타납니다.  
  
## <a name="quickwatch-dialog-box"></a>간략한 조사식 대화 상자  
 합니다 **간략 한 조사식** 대화 상자 XPath 1.0 식을 평가 하는 데 사용 됩니다. 컨텍스트 노드(지역 창의 `self::node()` 노드)는 XPath 식을 실행하기 위한 컨텍스트를 제공합니다. XPath 식을 실행한 결과는 조사식 창에 표시됩니다.  
  
 다음 목록에서는 XPath 식 계산에 대한 몇 가지 제한 사항을 설명합니다.  
  
- 기본 제공 XPath 함수만 사용할 수 있습니다.  
  
- `document()`, `key()` 등의 기본 제공 XSLT 함수는 사용할 수 없습니다.  
  
- 사용자 정의 함수는 사용할 수 없습니다.  
  
  자세한 내용은 [방법: XPath 식 계산](../xml-tools/how-to-evaluate-an-xpath-expression.md)합니다.  
  
## <a name="disassembly-window"></a>디스어셈블리 창  
 디스어셈블리 창에는 XSLT 컴파일러에서 생성된 어셈블리 코드가 표시됩니다. 다른 모든 Visual Studio 디스어셈블리 창과 같은 방법으로 이 창을 사용할 수 있습니다.  
  
 자세한 내용은 [방법: 디스어셈블리 창을 사용 하 여](../debugger/how-to-use-the-disassembly-window.md)입니다.  
  
## <a name="see-also"></a>참고 항목  
 [XSLT 디버깅](../xml-tools/debugging-xslt.md)   
 [Debugger Basics](../debugger/debugger-basics.md) (디버거 기본 사항)  
 [변수 창](https://msdn.microsoft.com/library/ce0a67f6-2502-4b7a-ba45-cc32f8aeba3e)

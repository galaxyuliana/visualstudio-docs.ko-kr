---
title: 도구 및 도구 상자 사용자 지정
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- vs.dsltools.dsldesigner.selectiondialog
- vs.dsltools.dsldesigner.selecticondialog
- vs.dsltools.dsldesigner.selectcursordialog
helpviewer_keywords:
- Domain-Specific Language, toolbox
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: da472f443f52a6478ac5e1e34fd4d4a5beb0721b
ms.sourcegitcommit: 51dad3e11d7580567673e0d426ab3b0a17584319
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2019
ms.locfileid: "66820825"
---
# <a name="customizing-tools-and-the-toolbox"></a>도구 및 도구 상자 사용자 지정

사용자가 모델에 추가할 수 있도록 할 요소에 대해 도구 상자 항목을 정의해야 합니다. 도구에는 요소 도구와 연결 도구의 두 가지 종류가 있습니다. 사용자는 생성된 디자이너에서 요소 도구를 선택해 도형을 다이어그램으로 끌고 연결 도구를 선택해 도형 간에 링크를 그릴 수 있습니다. 일반적으로 요소 도구를 사용하면 도메인 클래스 인스턴스를 모델에 추가할 수 있으며 연결 도구를 사용하면 도메인 관계 인스턴스를 추가할 수 있습니다.

## <a name="ToolboxDef"></a> 도구 상자를 정의 하는 방법
 DSL 탐색기에서 편집기 노드와 그 아래의 노드를 확장합니다. 일반적으로는 다음과 같은 계층 구조가 표시됩니다.

```
Editor
     Toobox Tabs
        MyDsl          //a tab
           Tools
               ExampleElement      // an element tool
               ExampleRelationship // a connection tool
```

DSL 탐색기의 이 부분에서 다음 작업을 수행할 수 있습니다.

- 새 탭 만들기. 탭은 도구 상자의 섹션 제목을 정의합니다.

- 새 도구 만들기

- 도구 복사/붙여넣기

- 도구를 목록에서 위/아래로 이동

- 탭과 도구 삭제

> [!IMPORTANT]
> DSL 탐색기에서 항목을 추가하거나 붙여넣으려면 새 노드의 상위 부모를 마우스 오른쪽 단추로 클릭합니다. 예를 들어 도구를 추가 하는 탭을 마우스 오른쪽 단추로 아니라 합니다 **도구** 노드. 탭을 추가 하려면 마우스 오른쪽 단추로 클릭 합니다 **편집기** 노드.

합니다 **도구 상자 아이콘** 속성의 모든 도구는 16 x 16 비트맵 파일을 참조 합니다. 이러한 파일에 일반적으로 유지 되는 **Dsl\Resources** 폴더입니다.

합니다 **클래스** 요소 도구의 속성은 구체적인 도메인 클래스를 참조 합니다. 도구는 기본적으로 이 클래스의 인스턴스를 만듭니다. 그러나 도구가 요소 그룹이나 다른 형식의 요소를 만들도록 코드를 작성할 수 있습니다.

합니다 **연결 작성기** 연결 도구의 속성 요소의 종류는 도구에 연결할 수 있고 간에 만드는 관계를 정의 하는 연결 작성기를 가리킵니다. 연결 작성기는 DSL 탐색기의 노드로 정의되며 도메인 관계를 정의할 때 자동으로 만들어지지만 연결 작성기를 사용자 지정하는 코드를 작성할 수 있습니다.

#### <a name="to-add-a-tool-to-the-toolbox"></a>도구 상자에 도구를 추가하려면

1. 요소 도구는 일반적으로 도형 클래스를 만들고 도메인 클래스에 매핑한 후 만듭니다.

     연결선 도구는 대개 연결선 클래스를 만들고 참조 관계에 매핑한 후 만듭니다.

2. DSL 탐색기에서 확장을 **편집기** 노드 및 **도구 상자 탭** 노드.

     도구 상자 탭 노드를 마우스 오른쪽 단추로 누른 **새 요소 도구 추가** 하거나 **새 연결 도구 추가**합니다.

3. 설정 된 **도구 상자 아이콘** 16 x 16 비트맵을 참조 하는 속성입니다.

     새 아이콘을 정의 하려는 경우 솔루션 탐색기에서 비트맵 파일을 만듭니다는 **Dsl\Resources** 폴더입니다. 파일에는 다음 속성 값을 있어야 합니다. **빌드 작업** = **콘텐츠**; **출력 디렉터리로 복사** = **복사 하지 않으려면**합니다.

4. **요소 도구의:** 설정 된 **클래스** 속성 도구의 모양에 매핑되는 구체적인 도메인 클래스를 참조 하세요.

     **커넥터 도구:** 설정 된 **연결 작성기** 도구의 드롭 다운 목록에서 제공 되는 항목 중 하나는 속성입니다. 연결 작성기는 연결선을 도메인 관계에 매핑하면 자동으로 만들어집니다. 최근에 연결선을 만든 경우에는 보통 연결된 연결 작성기를 선택합니다.

5. DSL을 테스트 하려면 F5 키나 ctrl+f5를 누르고 Visual Studio의 실험적 인스턴스에서 샘플 모델 파일을 엽니다. 도구 상자에 새 도구가 표시되어야 합니다. 해당 도구를 다이어그램으로 끌어 새 요소가 만들어지는지 확인합니다.

     도구 표시 되지 않는 경우 실험적 Visual Studio를 중지 합니다. Windows에서 **시작** 메뉴에서 실행할 **Microsoft Visual Studio 2010 실험적 인스턴스 재설정**합니다. **빌드** 메뉴에서 **솔루션 다시 빌드**를 클릭합니다. 그런 후에 DSL을 다시 테스트합니다.

## <a name="customizing"></a> 요소 도구 사용자 지정
 도구는 기본적으로 지정한 클래스의 단일 인스턴스를 만들지만 두 가지 방법을 통해 이 기본 옵션을 변경할 수 있습니다.

- 다른 클래스에 대해 요소 병합 지시문을 정의하여 해당 클래스가 이 클래스의 새 인스턴스를 수락하고 새 요소를 만들 때 추가 링크를 만들 수 있도록 설정합니다. 예를 들어 사용자가 다른 요소에 주석을 놓아 두 요소 간에 참조 링크를 만들도록 허용할 수 있습니다.

     이러한 사용자 지정은 사용자가 요소를 붙여넣거나 끌어서 놓을 때 수행되는 작업에도 영향을 줍니다.

     자세한 내용은 [사용자 지정 요소 만들기 및 이동](../modeling/customizing-element-creation-and-movement.md)합니다.

- 요소 그룹을 만들 수 있도록 도구를 사용자 지정하는 코드를 작성합니다. 그러면 도구가 재정의 가능한 ToolboxHelper.cs의 메서드를 통해 초기화됩니다. 자세한 내용은 [요소 그룹 만들기 도구에서](#groups)합니다.

## <a name="groups"></a> 도구에서 요소 그룹 만들기
 각 요소 도구는 만들어야 하는 요소의 프로토타입을 포함합니다. 기본적으로 각 요소 도구는 단일 요소를 만들지만 도구 하나로 관련 개체 그룹을 만들 수도 있습니다. 이렇게 하려면 관련 항목이 포함된 <xref:Microsoft.VisualStudio.Modeling.ElementGroupPrototype>을 사용하여 도구를 초기화합니다.

 다음 예제는 Transistor 형식이 포함된 DSL에서 가져온 것입니다. 각 Transistor에는 명명된 Terminal 세 개가 있습니다. Transistor용 요소 도구는 모델 요소 4개와 관계 링크 3개가 포함된 프로토타입을 저장합니다. 사용자가 도구를 다이어그램으로 끌면 프로토타입이 인스턴스화되어 모델 루트에 연결됩니다.

 이 코드에 정의 된 메서드를 재정의 **Dsl\GeneratedCode\ToolboxHelper.cs**합니다.

 프로그램 코드를 사용 하 여 모델을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [탐색 및 업데이트 프로그램 코드에서 모델](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.

```
using Microsoft.VisualStudio.Modeling;
using Microsoft.VisualStudio.Modeling.Diagrams;

  public partial class CircuitsToolboxHelper
  {
    /// <summary>
    /// Toolbox initialization, called for each element tool on the toolbox.
    /// This version deals with each Component subtype separately.
    /// </summary>
    /// <param name="store"></param>
    /// <param name="domainClassId">Identifies the domain class this tool should instantiate.</param>
    /// <returns>prototype of the object or group of objects to be created by tool</returns>
    protected override ElementGroupPrototype CreateElementToolPrototype(Store store, Guid domainClassId)
    {
        if (domainClassId == Transistor.DomainClassId)
        {
            Transistor transistor = new Transistor(store);

            transistor.Base = new ComponentTerminal(store);
            transistor.Collector = new ComponentTerminal(store);
            transistor.Emitter = new ComponentTerminal(store);

            transistor.Base.Name = "base";
            transistor.Collector.Name = "collector";
            transistor.Emitter.Name = "emitter";

            // Create an ElementGroup for the Toolbox.
            ElementGroup elementGroup = new ElementGroup(store.DefaultPartition);
            elementGroup.AddGraph(transistor, true);
            // AddGraph includes the embedded parts

            return elementGroup.CreatePrototype();
        }
        else
        {
            return base.CreateElementToolPrototype(store, domainClassId);
}  }    }
```

## <a name="connections"></a> 연결 도구 사용자 지정
 일반적으로는 새 연결선 클래스를 만들 때 요소 도구를 만듭니다. 두 도구의 형식을 통해 관계 형식을 결정하도록 허용하여 도구 하나를 재정의할 수도 있습니다. 예를 들어 사용자 간 관계와 사용자 대 지역 관계를 모두 만들 수 있는 연결 도구 하나를 정의할 수 있습니다.

 연결 도구는 연결 작성기를 호출합니다. 연결 작성기를 통해 사용자가 생성된 디자이너에서 요소를 연결할 수 있는 방법을 지정합니다. 연결 작성기는 연결 가능한 요소 및 해당 요소 간에 작성되는 링크의 종류를 지정합니다.

 도메인 클래스 간에 참조 관계를 만들면 연결 작성기가 자동으로 만들어집니다. 연결 도구를 매핑할 때 이 연결 작성기를 사용할 수 있습니다. 연결 도구를 만드는 방법에 대 한 자세한 내용은 참조 하세요. [도구 상자 구성](../modeling/customizing-tools-and-the-toolbox.md)합니다.

 기본 연결 작성기가 다른 소스 및 대상 형식 범위를 처리하고 다른 관계 형식을 만들도록 수정할 수 있습니다.

 또한 연결 작성기에 대해 사용자 지정 코드를 작성하여 연결의 소스 및 대상 클래스를 지정하고 설정할 연결 형식을 정의하며 연결 작성과 관련된 기타 작업을 수행할 수 있습니다.

### <a name="the-structure-of-connection-builders"></a>연결 작성기의 구조
 연결 작성기는 도메인 관계와 소스/대상 요소를 지정하는 링크 연결 지시문을 하나 이상 포함합니다. 예를 들어 작업 흐름 솔루션 템플릿에서 보면 합니다 **CommentReferencesSubjectsBuilder** 에 **DSL 탐색기**합니다. 이 연결 작성기에 대 한 링크 연결 지시문 **CommentReferencesSubjects**, 도메인 관계에 매핑되는 **CommentReferencesSubjects**합니다. 이 링크 연결 지시문은 `Comment` 도메인 클래스를 가리키는 소스 역할 지시문과 `FlowElement` 도메인 클래스를 가리키는 대상 역할 지시문을 포함합니다.

### <a name="using-connection-builders-to-restrict-source-and-target-roles"></a>연결 작성기를 사용하여 소스 및 대상 역할 제한
 연결 작성기를 사용하여 지정된 도메인 관계의 소스 역할 또는 대상 역할에서 특정 클래스의 발생을 제한할 수 있습니다. 다른 도메인 클래스에 대한 도메인 관계가 포함된 기본 도메인 클래스가 있는데 기본 클래스의 모든 파생된 클래스가 해당 관계에서 같은 역할을 포함하지 않도록 지정하려는 경우를 예로 들 수 있습니다. 작업 흐름 솔루션에는 구체적인 도메인 클래스 4 (**StartPoint**, **끝점**하십시오 **MergeBranch**, 및 **동기화**) 추상 도메인 클래스에서 직접 상속 하는 **FlowElement**를 두 구체적인 도메인 클래스 및 (**태스크** 하 고 **ObjectInState**)는 간접적으로 상속 것입니다. 이기도 한 **흐름** 참조 하는 관계 **FlowElement** 소스 역할과 대상 역할 모두의 도메인 클래스입니다. 그러나의 인스턴스를 **끝점** 도메인 클래스에는 인스턴스의 소스를 사용 해야 합니다.는 **흐름** 관계 인스턴스의 해야 하거나를 **StartPoint** 클래스는 대상의 인스턴스를 **흐름** 관계입니다. **FlowBuilder** 연결 작성기에 링크 연결 지시문 **흐름** 를 지정 하는 도메인 클래스는 소스 역할을 수행할 수 있습니다 (**태스크**,  **MergeBranch**, **StartPoint**, 및 **동기화**)는 대상 역할을 재생할 수 있습니다 (**MergeBranch**,  **끝점**, 및 **동기화**).

### <a name="connection-builders-with-multiple-link-connect-directives"></a>여러 링크 연결 지시문이 포함된 연결 작성기
 연결 작성기에 링크 연결 지시문을 두 개 이상 추가할 수 있습니다. 이 위해 사용자의 도메인 모델의 복잡성 중 일부를 숨기기를 유지 합니다 **도구 상자** 너무 복잡해 지지에서. 서로 다른 여러 도메인 관계에 대한 링크 연결 지시문을 단일 연결 작성기에 추가할 수 있습니다. 그러나 대략적으로 비슷한 기능을 수행하는 도메인 관계는 결합해야 합니다.

 작업 흐름 솔루션에는 **흐름** 연결 도구 둘 다의 인스턴스를 그리는 데 사용 되는 **흐름** 및 **ObjectFlow** 도메인 관계입니다. 합니다 **FlowBuilder** 연결 작성기에, 또한 합니다 **흐름** 라는 두 개의 링크 연결 지시문에 링크 연결 지시문 앞에서 설명한 **ObjectFlow**합니다. 이러한 지시어를 지정 하는 인스턴스에 **ObjectFlow** 인스턴스 간에 관계를 그릴 수는 **ObjectInState** 도메인 클래스 또는 인스턴스에서 **ObjectInState**  인스턴스에 **태스크**의 두 인스턴스 간이 아니라는 **작업**, 또는 인스턴스에서 **작업** 인스턴스에 **ObjectInState**합니다. 그러나의 인스턴스를 **흐름** 의 두 인스턴스 간의 관계를 그릴 수는 **작업**합니다. 를 컴파일하고 작업 흐름 솔루션을 실행 하는 경우 해당 그리기를 볼 수 있습니다는 **흐름** 인스턴스에서 **ObjectInState** 인스턴스에 **태스크** 의 인스턴스를 만듭니다는 **ObjectFlow**, 하지만 그리기를 **흐름** 의 두 인스턴스 간에 **태스크** 의 인스턴스를 만듭니다를 **흐름**합니다.

### <a name="custom-code-for-connection-builders"></a>연결 작성기용 사용자 지정 코드
 사용자 인터페이스에는 연결 작성기의 여러 사용자 지정 형식을 정의하는 4개 확인란이 있습니다.

- 합니다 **Custom accept** 확인란 원본 또는 대상 역할 지시문

- 합니다 **Custom connect** 확인란 원본 또는 대상 역할 지시문

- 합니다 **사용자 지정 연결을 사용 하 여** 확인란 연결 지시문

- 합니다 **Is Custom** 연결 작성기의 속성

  이러한 사용자 지정을 수행하려면 프로그램 코드를 입력해야 합니다. 입력해야 하는 코드를 확인하려면 위의 확인란 중 하나를 선택하고 모든 템플릿 변환을 클릭한 후에 솔루션을 빌드합니다. 그러면 오류 보고서가 표시됩니다. 오류 보고서를 두 번 클릭하면 추가해야 하는 코드를 설명하는 주석이 표시됩니다.

> [!NOTE]
> 사용자 지정 코드를 추가하려면 GeneratedCode 폴더의 코드 파일이 아닌 별도의 코드 파일에 부분 클래스 정의를 만듭니다. 작업 내용 손실을 방지하려면 생성된 코드 파일을 편집해서는 안 됩니다. 자세한 내용은 [생성 된 클래스 재정의 및 확장](../modeling/overriding-and-extending-the-generated-classes.md)합니다.

#### <a name="creating-custom-connection-code"></a>사용자 지정 연결 코드 만들기
 각 링크 연결 지시문을 **소스 역할 지시문** 탭에서 정의 끌어 놓을 수 있는 형식을 합니다. 마찬가지로, 합니다 **대상 역할 지시문** 탭에 대 한 정의 끌어 놓을 수 있는 형식을 합니다. 각 형식에 대 한 추가 지정할 수 있습니다 (에 대 한 해당 링크 연결 지시문)을 설정 하 여 연결을 허용 하도록 여부는 **Custom Accept** 플래그 및 다음 추가 코드를 제공 합니다.

 연결 설정 시 수행되는 작업도 사용자 지정할 수 있습니다. 예를 들어 특정 클래스에서/클래스로 끌기가 수행되는 경우만 사용자 지정하거나 단일 링크 연결 지시문이 적용되는 모든 경우를 사용자 지정하거나 전체 FlowBuilder 연결 작성기를 사용자 지정할 수 있습니다. 이러한 각 옵션에 대해 사용자 지정 플래그를 적절한 수준으로 설정할 수 있습니다. 모든 템플릿을 변환하고 솔루션 빌드를 시도하는 경우 오류 메시지에 생성된 코드의 주석이 표시됩니다. 이러한 주석을 통해 입력해야 하는 코드를 확인할 수 있습니다.

 구성 요소 다이어그램 샘플에서는 Connection 도메인 관계의 연결 작성기가 사용자 지정되어 포트 간에 설정할 수 있는 연결을 제한합니다. 다음 그림에서는 `OutPort` 요소에서 `InPort` 요소로만 연결할 수 있지만 각 요소를 서로 중첩할 수 있음을 보여줍니다.

 **중첩된 된 구성 요소에서 OutPort로 들어오는 연결**

 ![연결 작성기](../modeling/media/connectionbuilder_3.png)

 따라서 중첩된 구성 요소에서 OutPort로의 연결이 가능하도록 지정할 수 있습니다. 설정한 연결을 지정 하려면 **Uses Custom Accept** 에 **InPort** 원본 역할 유형 및 **OutPort** 형식을 대상 역할로 **DSL 세부 정보**  다음 그림과에서 같이 창:

 **DSL 탐색기의 링크 연결 지시문**

 ![연결 작성기 이미지](../modeling/media/connectionbuilder_4a.png)

 **링크 연결 지시문 DSL 세부 정보 창에서**

 ![링크 연결 지시문 DSL 세부 정보 창에서](../modeling/media/connectionbuilder_4b.png)

 그런 다음 ConnectionBuilder 클래스에서 메서드를 입력해야 합니다.

```
  public partial class ConnectionBuilder
  {
    /// <summary>
    /// OK if this component has children
    /// </summary>
    private static bool CanAcceptInPortAsSource(InPort candidate)
    {
       return candidate.Component.Children.Count > 0;
    }

    /// <summary>
    /// Only if source is on parent of target.
    /// </summary>
    private static bool CanAcceptInPortAndInPortAsSourceAndTarget                (InPort sourceInPort, InPort targetInPort)
    {
      return sourceInPort.Component == targetInPort.Component.Parent;
    }
// And similar for OutPorts...
```

 프로그램 코드를 사용 하 여 모델을 사용자 지정 하는 방법에 대 한 자세한 내용은 참조 하세요. [탐색 및 업데이트 프로그램 코드에서 모델](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.

 예를 들어 비슷한 코드를 통해 사용자가 부모-자식 링크를 포함하는 루프를 만들지 못하도록 지정할 수 있습니다. 이러한 제한 사항은 사용자가 언제 든 지 위반할 수 없습니다 때문에 '하드' 제약 조건으로 간주 됩니다. 또한 사용자가 저장할 수 없는 잘못 된 구성을 만들어 일시적으로 무시할 수 있는 '소프트' 유효성 검사를 만들 수 있습니다.

### <a name="good-practice-in-defining-connection-builders"></a>적절한 연결 작성기 정의 사례
 개념적으로 관련이 있는 경우에만 단일 연결 작성기가 여러 관계 형식을 만들도록 정의해야 합니다. 작업 흐름 샘플에서는 같은 작성기를 사용하여 작업 간에 그리고 작업과 개체 간에 흐름을 만듭니다. 그러나 같은 작성기를 사용해 주석과 작업 간에 관계를 만들면 관계를 혼동할 수도 있습니다.

 여러 관계 형식에 대해 연결 작성기 하나를 정의하는 경우에는 연결 작성기가 같은 소스 및 대상 개체 쌍의 형식 두 개 이상과 일치하지 않도록 해야 합니다. 이렇게 하지 않으면 결과를 예측할 수가 없습니다.

 사용자 지정 코드를 사용 하 여 '하드' 제약 조건을 적용 하지만 사용자가 일시적으로 잘못 된 연결을 변경할 수 있어야 하는지 여부를 고려해 야 합니다. 사용자가 일시적으로 잘못된 연결을 설정할 수 있어야 하는 경우에는 사용자가 변경 내용을 저장할 때까지 연결 유효성을 검사하지 않도록 제약 조건을 수정할 수 있습니다.

## <a name="see-also"></a>참고 항목

- [요소 만들기 및 이동 사용자 지정](../modeling/customizing-element-creation-and-movement.md)
- [복사 동작 사용자 지정](../modeling/customizing-copy-behavior.md)
- [방법: 끌어서 놓기 처리기 추가](../modeling/how-to-add-a-drag-and-drop-handler.md)
- [프로그램 코드에서 모델 탐색 및 업데이트](../modeling/navigating-and-updating-a-model-in-program-code.md)
- [회로 다이어그램 샘플 DSL](https://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)
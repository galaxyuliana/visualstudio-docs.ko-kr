---
title: DslDefinition.dsl 파일 | Microsoft Docs
ms.date: 11/15/2016
ms.prod: visual-studio-dev14
ms.technology: vs-ide-modeling
ms.topic: conceptual
helpviewer_keywords:
- Domain-Specific Language, definition file
ms.assetid: f3fc3ed7-2438-4e5a-b3d7-fe7e0e8a134c
caps.latest.revision: 24
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 610d371fe288a6582cdf9e6460c339347f60c81a
ms.sourcegitcommit: 08fc78516f1107b83f46e2401888df4868bb1e40
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2019
ms.locfileid: "65680835"
---
# <a name="the-dsldefinitiondsl-file"></a>DslDefinition.dsl 파일
[!INCLUDE[vs2017banner](../includes/vs2017banner.md)]

Dsl 프로젝트의 DslDefinition.dsl 파일의 구조에 설명를 [!INCLUDE[dsl](../includes/dsl-md.md)] 정의 하는 솔루션을 *도메인별 언어*합니다. DslDefinition.dsl 파일 클래스 및 관계를 다이어그램, 도형, 커넥터, serialization 형식으로 함께 도메인 특정 언어를 설명 하 고 **도구 상자** 도메인 특정 언어의 고 편집 도구입니다. DSL 솔루션에서 이러한 도구를 정의하는 코드는 DslDefinition.dsl 파일의 정보에 따라 생성됩니다.  
  
 일반적으로 사용 합니다 *도메인별 언어 디자이너* DslDefinition.dsl 파일을 편집 합니다. 그러나 DslDefinition.dsl 파일은 원시 형식이 XML이므로 XML 편집기에서도 열 수 있습니다. 파일에 포함된 정보와 디버깅 및 확장용으로 파일이 구성되는 방식을 파악하면 유용할 수 있습니다.  
  
 이 항목의 예제는 구성 요소 다이어그램 템플릿에서 발췌한 것입니다. 해당 예제를 확인하려면 구성 요소 모델 솔루션 템플릿을 기반으로 DSL(Domain-Specific Language) 솔루션을 만듭니다. 솔루션을 만들고 나면 DSL(Domain-Specific Language) Designer에 DslDefinition.dsl 파일이 표시됩니다. 파일을 닫습니다에서 마우스 오른쪽 단추로 클릭 **솔루션 탐색기**, 가리킨 **연결**, 클릭 **XML 편집기**를 클릭 하 고 **확인**합니다.  
  
## <a name="sections-of-the-dsldefinitiondsl-file"></a>DslDefinition.dsl 파일의 섹션  
 루트 요소는 \<Dsl >, 도메인 특정 언어, 네임 스페이스의 이름을 식별 하는 해당 특성 및 버전 관리에 대 한 주 및 부 버전 번호입니다. `DslDefinitionModel` 스키마는 유효한 DslDefinition.dsl 파일의 내용과 구조를 정의합니다.  
  
 자식 요소는 \<Dsl > 루트 요소는 다음과 같습니다.  
  
 클래스  
 이 섹션은 생성된 코드에서 클래스를 생성하는 각 도메인 클래스를 정의합니다.  
  
 관계  
 이 섹션은 모델의 각 관계를 정의합니다. 소스와 대상이 관계의 양쪽을 나타냅니다.  
  
 유형  
 이 섹션은 각 형식과 해당 네임스페이스를 정의합니다. 도메인 속성에는 두 가지 형식이 있습니다. `DomainEnumerations`는 모델에서 정의되며 형식을 DomainModel.cs에 생성합니다. `ExternalTypes`는 `String`, `Int32` 등 다른 위치에서 정의되며 아무 항목도 생성하지 않는 형식을 지칭합니다.  
  
 도형  
 이 섹션은 디자이너에서 모델이 표시되는 방식을 설명하는 모양을 정의합니다. 이러한 기하학적 모양은 다이어그램 섹션에서 모델의 클래스에 매핑됩니다.  
  
 연결선  
 이 섹션은 디자이너에 표시되는 연결선의 모양을 정의합니다. 이러한 기하학적 스타일 설명은 다이어그램 섹션에서 모델의 특정 관계에 매핑됩니다.  
  
 XmlSerializationBehavior  
 이 섹션은 serialization 체계를 정의하며 각 클래스가 파일에 저장되는 방법에 대한 추가 정보를 제공합니다.  
  
 ExplorerBehavior  
 이 섹션에서는 정의 하는 방법을 **DSL 탐색기** 창은 사용자가 모델을 편집할 때 나타납니다.  
  
 ConnectionBuilders  
 이 섹션은 각 연결선 도구(연결할 수 있는 두 클래스 간에 링크를 만드는 도구)용 연결 작성기를 정의합니다. 이 섹션에서 소스 및 대상 클래스에 연결할 수 있는지 여부가 결정됩니다.  
  
 다이어그램  
 이 섹션은 다이어그램을 정의합니다. 배경색, 루트 클래스 등의 속성을 지정하는 데 해당 다이어그램을 사용합니다. 루트 클래스는 전체 다이어그램으로 표시되는 도메인 클래스입니다. Diagram 섹션에는 각 도메인 클래스 또는 관계를 나타내는 모양이나 연결선을 지정하는 ShapeMap 및 ConnectorMap 요소도 포함됩니다.  
  
 Designer  
 이 섹션에서는 모아 놓은 디자이너 (편집기)를 정의 **도구 상자**, 유효성 검사 설정, 다이어그램 및 serialization 체계입니다. Designer 섹션에서는 모델의 루트 클래스(대개 다이어그램의 루트 클래스이기도 함)도 정의합니다.  
  
 Explorer  
 이 섹션에서는 합니다 **DSL 탐색기** 동작 (XmlSerializationBehavior 섹션에 정의 됨).  
  
## <a name="monikers-in-the-dsldefinitiondsl-file"></a>DslDefinition.dsl 파일의 모니커  
 DslDefinition.dsl 파일 전체에서 모니커를 사용하여 특정 항목에 대한 상호 참조를 만들 수 있습니다. 예를 들어 각 관계 정의에는 Source 하위 섹션과 Target 하위 섹션이 포함됩니다. 각 하위 섹션은 해당 관계와 연결할 수 있는 개체 클래스의 모니커를 포함합니다.  
  
```  
<DomainRelationship …        Name="LibraryHasMembers" Namespace="ExampleNamespace" >    <Source>      <DomainRole …>  
       <RolePlayer>  
         <DomainClassMoniker Name="Library" />  
       </RolePlayer>  
     </DomainRole>  
   </Source>  
```  
  
 보통 참조되는 항목(이 예에서는 `Library` 도메인 클래스)의 네임스페이스는 참조하는 항목(여기서는 LibraryHasMembers 도메인 관계)과 같습니다. 이러한 경우 모니커는 클래스 이름만 제공해야 합니다. 그렇지 않으면 /Namespace/Name의 전체 형식을 사용해야 합니다.  
  
```  
  
<DomainClassMoniker Name="/ExampleNameSpace/Library" />  
  
```  
  
 모니커 시스템을 사용하려면 XML 트리의 형제에 고유한 이름이 지정되어 있어야 합니다. 그러므로 예를 들어 이름이 같은 클래스가 두 개 포함된 DSL 정의를 저장하려고 하면 유효성 검사 오류가 발생합니다. 나중에 정상적으로 다시 로드할 수 있도록 항상 DslDefinition.dsl 파일을 저장하기 전에 이러한 중복 이름 오류를 해결해야 합니다.  
  
 각 형식에는 자체 모니커 형식인에 있습니다. DomainClassMoniker, DomainRelationshipMoniker 및 등입니다.  
  
## <a name="types"></a>유형  
 Types 섹션은 DslDefinition.dsl 파일이 속성 형식으로 포함하는 모든 형식을 지정합니다. 이러한 형식에는 System.String과 같은 외부 형식과 열거 형식의 두 가지 종류가 있습니다.  
  
### <a name="external-types"></a>외부 형식  
 구성 요소 다이어그램 예에는 표준 기본 형식 집합이 나와 있습니다. 그러나 실제로는 해당 형식 중 일부만 사용됩니다.  
  
 각 외부 형식 정의는 String 및 System과 같은 이름과 문자열로만 구성됩니다.  
  
```  
<ExternalType Name="String" Namespace="System" />  
```  
  
 "string"과 같은 해당 컴파일러 키워드가 아닌 전체 형식 이름이 사용됩니다.  
  
 외부 형식은 표준 라이브러리 형식으로 제한되지 않습니다.  
  
### <a name="enumerations"></a>열거형  
 일반적인 열거형 사양은 다음 예와 비슷합니다.  
  
```  
<DomainEnumeration IsFlags="true" Name="PageSort"          Namespace="Fabrikam.Wizard">  
  <Literals>  
    <EnumerationLiteral Name="Start" Value="1"/>  
    <EnumerationLiteral Name="Decision" Value="2"/>  
  </Literals>  
</DomainEnumeration>  
```  
  
 `IsFlags` 특성은 `[Flags]` CLR(공용 언어 런타임) 특성에 의해 생성된 코드에 접두사가 적용되는지 여부를 제어합니다. 이 특성은 열거형 값을 비트로 결합할 수 있는지 여부를 결정합니다. 이 특성을 true로 설정하면 리터럴 값에 대해 2의 거듭제곱 값을 지정해야 합니다.  
  
## <a name="classes"></a>클래스  
 DSL 정의에 포함되는 대부분의 요소는 직간접적으로 `DomainClass`의 인스턴스입니다. `DomainClass`의 서브클래스에는 `DomainRelationship`, `Shape`, `Connector`, `Diagram` 등이 있습니다. DslDefinition.dsl 파일의 `Classes` 섹션에는 도메인 클래스가 나열됩니다.  
  
 각 클래스에는 속성 집합이 있으며 기본 클래스도 있을 수 있습니다. 구성 요소 다이어그램 예제에서 `NamedElement`는 `Name` 속성을 포함하는 추상 클래스로, 해당 형식은 문자열입니다.  
  
```  
<DomainClass Id="ee3161ca-2818-42c8-b522-88f50fc72de8"  Name="NamedElement" Namespace="Fabrikam.CmptDsl5"      DisplayName="Named Element"  InheritanceModifier="Abstract">  
  <Properties>  
    <DomainProperty Id="ef553cf0-33b5-4e34-a30b-cfcfd86f2261"   Name="Name" DisplayName="Name"  DefaultValue="" Category="" IsElementName="true">  
      <Type>  
        <ExternalTypeMoniker Name="/System/String" />  
      </Type>  
    </DomainProperty>  
  </Properties>  
</DomainClass>  
```  
  
 `NamedElement`는 `Component`와 같은 여러 기타 클래스의 기준 클래스이며, 자체 속성과 함께 `Name`에서 상속되는 `NamedElement` 속성도 포함합니다. BaseClass 자식 노드는 모니커 참조를 포함합니다. 참조되는 클래스가 같은 네임스페이스에 있으므로 모니커에는 해당 이름만 필요합니다.  
  
```  
<DomainClass Name="Component" Namespace="Fabrikam.CmptDsl5"              DisplayName="Component">  
  <BaseClass>  
    <DomainClassMoniker Name="NamedElement" />  
  </BaseClass>  
  <Properties>  
    <DomainProperty Name="Kind" DisplayName="Kind" >  
      <Type>  
        <ExternalTypeMoniker Name="/System/String" />  
      </Type>  
    </DomainProperty>  
  </Properties>  
```  
  
 관계, 모양, 연결선, 다이어그램을 포함한 모든 도메인 클래스는 다음 특성과 자식 노드를 포함할 수 있습니다.  
  
- **Id.** 이 특성은 GUID입니다. 파일에서 값을 제공하지 않으면 DSL(Domain-Specific Language) Designer에서 값을 만듭니다. 이 문서의 그림에서는 공간을 절약하기 위해 이 특성을 대부분 생략합니다.  
  
- **이름 및 Namespace입니다.** 이러한 특성에 생성된 된 코드에서 클래스의 네임 스페이스와 이름을 지정합니다. 이 두 특성은 DSL에서 모두 고유해야 합니다.  
  
- **InheritanceModifier.** 이 특성이 "abstract", "sealed" 또는 none입니다.  
  
- **DisplayName.** 이 특성은 이름에 표시 되는 **속성** 창입니다. DisplayName 특성은 공백과 기타 문장 부호를 포함할 수 있습니다.  
  
- **GeneratesDoubleDerived.** 이 특성이로 설정 된 경우 true 이면 두 클래스가 생성 되며, 않으며 하나가 다른 서브 클래스입니다. 생성된 모든 메서드는 기본 클래스에 있으며 생성자는 서브클래스에 있습니다. 이 특성을 설정하면 사용자 지정 코드에서 생성된 메서드를 재정의할 수 있습니다.  
  
- **HasCustomConstructor**. 이 특성을 true로 설정하면 생성된 코드에서 생성자가 생략되어 원하는 버전을 직접 작성할 수 있습니다.  
  
- **특성**합니다. 이 특성은 생성된 클래스의 CLR 특성을 포함합니다.  
  
- **BaseClass**합니다. 기본 클래스를 지정하는 경우 형식이 같아야 합니다. 예를 들어 도메인 클래스는 다른 도메인 클래스를 기본 클래스로 포함해야 하며 구획 모양은 구획 모양을 포함해야 합니다. 기본 클래스를 지정하지 않으면 생성된 코드의 클래스가 표준 프레임워크 클래스에서 파생됩니다. 예를 들어 도메인 클래스는 `ModelElement`에서 파생됩니다.  
  
- **속성**합니다. 이 특성은 트랜잭션 제어 하에 유지 관리되며 모델 저장 시 영구 저장되는 속성을 포함합니다.  
  
- **ElementMergeDirectives**. 각 요소 병합 지시문은 타 클래스의 다른 인스턴스가 부모 클래스 인스턴스에 추가되는 방법을 제어합니다. 요소 병합 지시문에 대한 자세한 내용은 이 항목 뒷부분에서 확인할 수 있습니다.  
  
- `Classes` 섹션에 나열된 각 도메인 클래스에 대해 C# 클래스가 생성됩니다. C# 클래스는 Dsl\GeneratedCode\DomainClasses.cs에 생성됩니다.  
  
### <a name="properties"></a>속성  
 각 도메인 속성에는 이름과 형식이 있습니다. 이름은 도메인 클래스 및 전이 기준에서 고유해야 합니다.  
  
 형식은 `Types` 섹션에 나열된 형식 중 하나를 지칭해야 합니다. 일반적으로 모니커는 네임스페이스를 포함해야 합니다.  
  
```  
<DomainProperty Name="Name" DisplayName="Name"  DefaultValue="" Category="" IsElementName="true">  
  <Type>  
    <ExternalTypeMoniker Name="/System/String" />  
  </Type>  
</DomainProperty>  
```  
  
 각 도메인 속성은 다음 특성도 포함할 수 있습니다.  
  
- **IsBrowsable**합니다. 이 특성에 해당 속성이 표시 여부를 결정 합니다 **속성** 부모 클래스의 개체를 클릭할 때 창이 있습니다.  
  
- **IsUIReadOnly**. 이 특성을 사용자의 속성을 변경할 수 있는지 여부를 결정 합니다 **속성** 창 또는 속성이 표시 되는 데코레이터를 통해.  
  
- **종류**합니다. 이 특성은 Normal, Calculated 또는 CustomStorage로 설정해야 합니다. 이 특성을 Calculated로 설정하는 경우 값을 결정하는 사용자 지정 코드를 제공해야 하며 속성은 읽기 전용이 됩니다. 이 특성을 CustomStorage로 설정하는 경우에는 값을 가져오고 설정하는 코드를 제공해야 합니다.  
  
- **IsElementName**합니다. 이 특성을 true로 설정하면 부모 클래스 인스턴스를 만들 때 해당 값이 고유한 값으로 자동 설정됩니다. 각 클래스에서 문자열 형식이어야 하는 속성 하나에 대해서만 이 특성을 true로 설정할 수 있습니다. 구성 요소 다이어그램 예제에서는 `Name`의 `NamedElement` 속성에서 `IsElementName`이 true로 설정되어 있습니다. 따라서 사용자가 `Component`에서 상속하는 `NamedElement` 요소를 만들 때마다 이름이 "Component6"처럼 자동으로 초기화됩니다.  
  
- `DefaultValue`. 이 특성을 지정한 경우 지정한 값이 이 클래스의 새 인스턴스에 대해 이 특성에 할당됩니다. `IsElementName`이 설정되어 있으면 DefaultValue 특성은 새 문자열의 시작 부분을 지정합니다.  
  
- **범주** 는 헤더에 속성이 표시 되는 **속성** 창입니다.  
  
## <a name="relationships"></a>관계  
 `Relationships` 섹션에는 DSL의 모든 관계가 나열됩니다. 모든 `Domain Relationship`은 이진이며 방향이 지정되어 소스 클래스 멤버를 대상 클래스 멤버에 연결합니다. 소스 클래스와 대상 클래스는 보통 도메인 클래스이지만 다른 관계에 대한 관계도 허용됩니다.  
  
 OutPort 클래스 멤버를 InPort 클래스 멤버에 연결하는 Connection 관계를 예로 들어 보겠습니다. 여기서 관계의 각 링크 인스턴스는 OutPort 인스턴스를 InPort 인스턴스에 연결합니다. 이 관계는 다대다 관계이므로 각 OutPort는 해당 인스턴스를 소스로 사용하는 여러 Connection 링크를 포함할 수 있고 각 InPort 인스턴스도 해당 인스턴스를 대상으로 사용하는 여러 Connection 링크를 포함할 수 있습니다.  
  
### <a name="source-and-target-roles"></a>소스 및 대상 역할  
 각 역할은 다음 특성이 들어 있는 소스 및 대상 역할을 포함합니다.  
  
- `RolePlayer` 특성은 연결 된 인스턴스의 도메인 클래스를 참조 합니다. OutPort InPort 대상에 대 한 원본에 대 한 합니다.  
  
- `Multiplicity` 특성에 사용 가능한 값은 네 가지로 ZeroMany, ZeroOne, One 및 OneMany가 있습니다. 이 특성은 역할 수행자 하나에 연결할 수 있는 이 관계의 링크 수를 나타냅니다.  
  
- `PropertyName` 특성은 반대쪽 개체에 액세스하기 위해 역할 수행 클래스에서 사용하는 이름을 지정합니다. 이 이름은 템플릿 또는 사용자 지정 코드에서 관계를 트래버스하는 데 사용됩니다. 예를 들어 소스 역할의 `PropertyName` 특성이 `Targets`로 설정되어 있으면 다음 코드가 작동합니다.  
  
    ```  
    OutPort op = …; foreach (InPort ip in op.Targets) ...  
    ```  
  
     규칙에 따라 다중성이 ZeroMany 또는 OneMany이면 속성 이름은 복수가 됩니다.  
  
     역할의 다중성이란 특정 역할의 각 인스턴스와 연결할 수 있는 반대쪽 역할의 수를 지칭합니다. 예를 들어 ComponentHasPorts 관계에서 대상 역할의 `RolePlayer` 특성은 Port로, `PropertyName` 특성은 Component로, `Multiplicity` 특성은 ZeroOne으로 설정되어 있습니다. 그렇다면 이 역할을 사용하는 데 적합한 코드는 다음과 같습니다.  
  
    ```  
    ComponentPort p = …; Component c = p.Component; if (c != null) …  
    ```  
  
- 역할의 `Name` 은 Relationship 클래스 내에서 해당 링크 쪽을 지칭하는 데 사용되는 이름입니다. 각 링크의 양쪽에는 인스턴스가 하나뿐이므로 규칙에 따라 역할 이름은 항상 단수입니다. 그러므로 다음과 같은 코드가 작동합니다.  
  
    ```  
    Connection connectionLink = …; OutPort op = connectionLink.Source;  
    ```  
  
- 기본적으로 `IsPropertyGenerator` 특성은 true로 설정됩니다. 이 특성을 false로 설정하면 역할 수행자 클래스에서 속성이 만들어지지 않습니다. 그러면 예를 들어 `op.Targets` 등의 코드는 작동하지 않습니다. 그러나 사용자 지정 코드를 사용하여 관계를 트래버스하거나 사용자 지정 코드가 관계를 명시적으로 사용하는 경우에는 링크 자체에 대한 액세스 권한을 얻을 수 있습니다.  
  
    ```  
    OutPort op = …; foreach (InPort ip in Connection.GetTargets(op)) …  
    foreach (Connection link in Connection.GetLinksToTargets(op)) …  
    ```  
  
### <a name="relationship-attributes"></a>관계 특성  
 모든 클래스에서 사용 가능한 특성 및 자식 노드 외에 각 관계에는 다음 클래스도 포함됩니다.  
  
- **IsEmbedding**. 이 부울 특성은 관계가 포함 트리의 일부분인지를 지정합니다. 모든 모델은 포함 관계로 트리를 형성해야 합니다. 따라서 모든 도메인 컨트롤러는 모델의 루트가 아니면 포함 관계 하나 이상의 대상이어야 합니다.  
  
- **AllowsDuplicates**. 기본적으로 false로 설정되는 이 부울 특성은 소스 및 대상 둘 다에서 다중성이 "다"인 관계에만 적용됩니다. 이 특성은 언어 사용자가 같은 관계의 링크 둘 이상을 사용하여 단일 소스 및 대상 요소 쌍을 연결할 수 있는지 여부를 결정합니다.  
  
## <a name="designer-and-toolbox-tabs"></a>Designer 및 ToolboxTab  
 주요 부분을 **디자이너** DslDefinition.dsl 파일의 섹션을 **ToolboxTab** 요소입니다. 이러한 요소를 각각 생성된 된 디자이너에서 제목이 지정 된 섹션을 나타내는 다양 한 디자이너 있을 수 있습니다 **도구 상자**합니다. 각 **ToolboxTab** 요소에는 하나 이상 포함 될 수 있습니다 **ElementTool** 요소인 **ConnectionTool** 요소 중 하나 또는 둘 다.  
  
 요소 도구는 특정 도메인 클래스 인스턴스를 만들 수 있습니다. 사용자가 요소 도구를 다이어그램으로 끌어 놓으면 이 항목 뒷부분의 요소 병합 지시문 관련 섹션에서 설명하는 요소 병합 지시문에 의해 결과가 결정됩니다.  
  
 각 연결 도구는 특정 연결 작성기를 호출할 수 있습니다. 연결 작성기 관련 섹션에서 설명하는 것처럼 사용자가 마우스를 클릭하는 위치에 따라 연결 작성기 하나가 둘 이상의 관계를 만들 수 있습니다.  
  
 이러한 형식의 도구에서는 모양이나 연결선을 직접 생성하지 않습니다. 각 도구는 도메인 클래스 또는 도메인 관계를 인스턴스화합니다. 그러면 모양 및 연결선 매핑에 따라 도메인 클래스 또는 도메인 관계 표시 방식이 결정됩니다.  
  
## <a name="paths"></a>경로  
 도메인 경로는 DslDefinition.dsl 파일의 여러 위치에 표시됩니다. 이러한 경로는 DSL 인스턴스인 모델 내 요소 간에 일련의 링크를 지정합니다. 경로 구문은 단순하지만 자세한 정보를 표시합니다.  
  
 경로는 DslDefinition.dsl 파일의 `<DomainPath>…</DomainPath>` 태그에 표시됩니다. 경로를 통해 여러 링크로 이동할 수는 있지만 대부분의 실제 예제에서는 링크 하나만 트래버스합니다.  
  
 경로는 세그먼트 시퀀스로 구성됩니다. 각 세그먼트는 개체에서 링크로 또는 링크에서 개체로의 홉입니다. 따라서 긴 경로에서는 대개 홉이 교대로 반복됩니다. 예를 들어 첫 번째 홉은 개체에서 링크로의 홉, 두 번째 홉은 링크 반대쪽 개체로의 홉, 세 번째 홉은 다음 링크로의 홉과 같은 식으로 반복될 수 있습니다. 단, 관계 자체가 다른 관계의 소스 또는 대상인 경우에는 이 시퀀스의 예외가 나타날 수 있습니다.  
  
 각 세그먼트는 관계 이름으로 시작됩니다. 개체에서 링크로의 홉에는 다음과 같이 관계 뒤에 점과 속성 이름이 붙습니다. "`Relationship . Property`" 링크에서 개체로의 홉에는 다음과 같이 관계 뒤에 느낌표와 역할 이름이 붙습니다. "`Relationship ! Role`"  
  
 구성 요소 다이어그램 예제에서는 InPort에 대한 ShapeMap의 ParentElementPath에 경로가 포함되어 있습니다. 이 경로는 다음과 같이 시작됩니다.  
  
```  
    ComponentHasPorts.Component  
```  
  
 이 예제에서 InPort는 ComponentPort의 서브클래스이며 ComponentHasPorts 관계를 포함합니다. 속성의 이름은 Component입니다.  
  
 를 작성할 때 C#이 모델에 대 한 각각의 관련 된 클래스의 관계를 생성 하는 속성을 사용 하 여 한 단계로 링크를 이동할 수 있습니다.  
  
```  
     InPort port; ...  Component c = port.Component;  
```  
  
 그러나 경로 구문에서 두 홉을 모두 명시적으로 지정해야 합니다. 이 요구 사항으로 인해 중간 링크에 보다 쉽게 액세스할 수 있습니다. 다음 코드는 링크에서 Component로의 홉을 완료합니다.  
  
```  
    ComponentHasPorts.Component / ! Component  
```  
  
 관계 이름이 이전 세그먼트와 같으면 생략해도 됩니다.  
  
## <a name="element-merge-directives"></a>요소 병합 지시문  
 언어 사용자가에서 항목을 끌 때 합니다 **도구 상자** 도구의 클래스의 인스턴스를 다이어그램으로 생성 됩니다. 그리고 해당 인스턴스와 기존 모델 요소 간에 링크가 만들어집니다. 언어를 끌 때까지 구성 요소나 주석 등 일부 항목은 생성 된 **도구 상자** 다이어그램의 빈 부분으로 합니다. 그 외의 항목은 언어 사용자가 다른 호스트 요소로 끌면 만들어집니다. 예를 들어 OutPort 또는 InPort는 언어 사용자가 구성 요소로 끌면 만들어집니다.  
  
 Component 등의 잠재적 호스트 클래스는 새 요소 클래스의 요소 병합 지시문을 포함하는 경우에만 새 요소를 수락합니다. 예를 들어 Name="Component"인 DomainClass 노드는 다음 코드를 포함합니다.  
  
```  
<DomainClass Name="Component" …> …  
    <ElementMergeDirective>  
      <Index>  
        <DomainClassMoniker Name="ComponentPort" />  
      </Index>  
      <LinkCreationPaths>  
        <DomainPath>ComponentHasPorts.Ports</DomainPath>  
      </LinkCreationPaths>  
    </ElementMergeDirective> …  
```  
  
 Index 노드 아래의 클래스 모니커는 수락할 수 있는 요소 클래스를 참조합니다. 여기서는 ComponentPort가 InPort 및 OutPort의 추상 클래스입니다. 따라서 이 두 요소 중 하나를 수락할 수 있습니다.  
  
 언어의 루트 클래스인 ComponentModel에는 구성 요소와 주석의 요소 병합 지시문이 있습니다. 다이어그램의 빈 부분은 루트 클래스를 나타내므로 언어 사용자는 이러한 클래스의 항목을 다이어그램으로 직접 끌 수 있습니다. 그러나 ComponentModel에는 ComponentPort의 요소 병합 지시문이 없습니다. 따라서 언어 사용자는 InPort 또는 OutPort를 다이어그램으로 직접 끌어 놓을 수 없습니다.  
  
 요소 병합 지시문은 새 요소를 기존 모델에 통합하거나 병합하기 위해 만들 수 있는 하나 이상의 링크를 결정합니다. ComponentPort의 경우에는 ComponentHasPorts 인스턴스가 만들어집니다. DomainPath는 새 요소가 추가되는 부모 클래스인 Ports의 속성과 관계를 모두 식별합니다.  
  
 둘 이상의 링크 만들기 경로를 포함하여 요소 병합 지시문에서 둘 이상의 링크를 만들 수 있습니다. 경로 중 하나는 포함되어야 합니다.  
  
 링크 만들기 경로 하나에서 둘 이상의 세그먼트를 사용할 수 있습니다. 이 경우 만들어야 하는 링크는 마지막 세그먼트가 정의합니다. 그 앞의 세그먼트는 부모 클래스에서 새 링크를 만들어야 하는 개체로 이동합니다.  
  
 예를 들어 Component 클래스에 다음 요소 병합 지시문을 추가할 수 있습니다.  
  
```  
<DomainClass Name="Component" …> …  
  <ElementMergeDirective>  
    <Index>  
       <DomainClassMoniker Name="Comment"/>  
    </Index>  
    <LinkCreationPaths>  
       <DomainPath>          ComponentModelHasComponents . ComponentModel / !ComponentModel         / ComponentModelHasComments.Comments       </DomainPath>  
       <DomainPath>CommentsReferenceComponents.Comments</DomainPath>  
    </LinkCreationPaths>  
  </ElementMergeDirective>  
```  
  
 그러면 언어 사용자가 주석을 구성 요소로 끌고 구성 요소에 대한 링크를 사용하여 새 주석을 자동으로 만들 수 있습니다.  
  
 첫 번째 링크 만들기 경로는 `Component`에서 `ComponentModel`로 이동한 다음 포함 관계 `ComponentModelHasComments`의 인스턴스를 만듭니다. 두 번째 링크 만들기 경로는 호스트 Component에서 새 Comment로 이동하는 참조 관계 CommentsReferenceComponents의 링크를 만듭니다. 모든 링크 만들기 경로는 호스트 클래스로 시작해야 하며 새로 인스턴스화된 클래스로 단계별 이동하는 링크에서 끝나야 합니다.  
  
## <a name="xmlclassdata"></a>XmlClassData  
 관계 및 하위 형식을 비롯한 각 도메인 클래스는 `XmlClassData` 노드에서 추가 정보를 제공할 수 있습니다. 이 노드는 DslDefinition.dsl 파일의 `XmlSerializationBehavior` 섹션에 표시됩니다. 이 정보는 모델을 파일에 저장할 때 클래스 인스턴스가 serialize된 형식으로 저장되는 방식을 구체적으로 지정합니다.  
  
 `XmlSerializationBehavior`가 적용되는 대부분의 생성된 코드는 `Dsl\GeneratedCode\Serializer.cs`에 들어 있습니다.  
  
 각 `XmlClassData` 노드는 다음 자식 노드 및 특성을 포함합니다.  
  
- 데이터가 적용되는 클래스를 참조하는 모니커 노드  
  
- **XmlPropertyData** 클래스에 정의 된 각 속성에 대 한 합니다.  
  
- **XmlRelationshipData** 클래스에서 소싱 된 각 관계에 대 한 합니다. 관계에는 자체 XmlClassData 노드도 있습니다.  
  
- **TypeName** 생성된 된 코드에서 serialization 도우미 클래스의 이름을 결정 하는 문자열 특성.  
  
- **ElementName** 이 클래스의 serialize 된 인스턴스 XML 태그를 결정 하는 문자열입니다. 규칙에 따라 ElementName은 첫 글자가 소문자라는 것을 제외하면 대개 클래스 이름과 같습니다. 다음 코드로 시작되는 샘플 모델 파일을 예로 들 수 있습니다.  
  
    ```  
    <componentModel …  
    ```  
  
- **MonikerElementName** 사용자의 serialize 된 모델 파일에 있습니다. 이 특성은 해당 클래스를 참조하는 모니커를 사용합니다.  
  
- **MonikerAttributeName**, 모니커 내의 XML 특성의 이름을 식별 합니다. 사용자의 serialize 된 파일의이 부분에서 도메인 특정 언어의 작성자는 다음과 같이 정의 됩니다. **MonikerElementName** "inPortMoniker"로 하 고 **MonikerAttributeName** 을 "path":  
  
    ```  
    <inPortMoniker path="//Component2/InPort1" />  
    ```  
  
### <a name="connectionbuilders"></a>ConnectionBuilders  
 각 연결 도구에 대해 연결 작성기가 정의됩니다. 각 연결 작성기는 하나 이상의 LinkConnectDirective 요소로 구성되며, 이러한 각 요소는 하나 이상의 SourceDirective 요소와 TargetDirective를 포함합니다. 사용자는 연결 도구를 클릭한 후 SourceDirective 요소의 목록에 표시되는 모델 요소에 매핑된 모양에서 연결을 시작할 수 있습니다. 그런 다음 TargetDirective 요소의 목록에 표시되는 요소에 매핑되는 모양에서 연결을 완료할 수 있습니다. 인스턴스화되는 관계의 클래스는 연결이 시작된 위치에 의해 지정되는 LinkConnectDirective 요소에 따라 달라집니다.  
  
### <a name="xmlpropertydata"></a>XmlPropertyData  
 A **DomainPropertyMoniker** 특성 데이터를 참조 하는 속성을 식별 합니다. 이 특성은 바깥쪽 ClassData 클래스의 속성이어야 합니다.  
  
 합니다 **XmlName** 특성이 XML에 표시 되어야 하는 대로 해당 특성 이름을 제공 합니다. 규칙에 따라 이 문자열은 첫 글자가 소문자라는 것을 제외하면 속성 이름과 같습니다.  
  
 기본적으로 **표현을** 특성은 Attribute로 설정 합니다. 하는 경우 **표현을** 자식 요소를 설정 하는 XML에 노드가 생성 됩니다. 하는 경우 **표현을** 는 Ignore로 설정 된 속성은 serialize 되지 않습니다.  
  
 합니다 **IsMonikerKey** 하 고 **IsMonikerQualifier** 특성 속성을 부모 클래스의 인스턴스를 식별 하는 역할을 부여 합니다. 설정할 수 있습니다 **IsMonikerKey** 에 정의 되어 있거나 클래스에서 상속 되는 속성 하나에 대해 true로 합니다. 이 특성은 부모 클래스의 개별 인스턴스를 식별합니다. `IsMonikerKey`로 설정하는 속성은 대개 이름 또는 기타 키 식별자입니다. 예를 들어 `Name` 문자열 속성은 NamedElement 및 해당 파생 클래스의 모니커 키입니다. 사용자가 모델을 파일에 저장할 때 이 특성은 각 인스턴스에 대한 고유 값과 포함 관계 트리의 형제를 포함해야 합니다.  
  
 serialize된 모델 파일에서 요소의 전체 모니커는 모델 루트에서 포함 관계 트리까지의 경로로, 각 지점에서 모니커 키를 인용합니다. InPort는 Component 내에 포함되고 Component는 모델 루트에 포함되는 경우를 예로 들면 올바른 모니커는 다음과 같습니다.  
  
```  
<inPortMoniker name="//Component2/InPort1" />  
```  
  
 설정할 수 있습니다 합니다 **IsMonikerQualifier** 문자열 속성에 대 한 특성 및 요소의 전체 이름을 생성 하는 추가 방법을 제공 합니다. DslDefinition.dsl 파일의 예를 들어 **Namespace** 는 모니커 한정자입니다.  
  
### <a name="xmlrelationshipdata"></a>XmlRelationshipData  
 serialize된 모델 파일 내에서 포함 관계와 참조 관계 둘 다의 링크는 관계 소스 끝의 자식 노드로 표시됩니다. 포함 관계의 경우 자식 노드에는 하위 트리가 포함됩니다. 참조 관계의 경우 자식 노드에는 트리의 다른 부분을 참조하는 모니커가 포함됩니다.  
  
 합니다 **XmlRelationshipData** 특성을 **XmlClassData** 특성 자식 노드는 원본 요소 안에 중첩 하는 방법에 정확 하 게 정의 합니다. 도메인 클래스의 소스인 모든 관계에 하나 **XmlRelationshipData** 특성입니다.  
  
 합니다 **DomainRelationshipMoniker** 특성 클래스를 소스로 관계 중 하나를 식별 합니다.  
  
 합니다 **RoleElementName** 특성은 직렬화 된 데이터에 자식 노드를 둘러싸는 XML 태그 이름을 제공 합니다.  
  
 예를 들어 DslDefinition.dsl 파일에는 다음 코드가 포함됩니다.  
  
```  
<XmlClassData ElementName="component" …>  
  <DomainClassMoniker Name="Component" />  
  <ElementData>  
    <XmlRelationshipData RoleElementName="ports">  
      <DomainRelationshipMoniker Name="ComponentHasPorts" />  
    </XmlRelationshipData>  
```  
  
 따라서 serialize된 파일에는 다음 코드가 포함됩니다.  
  
```  
<component name="Component1"> <!-- parent ->  
   <ports> <!-- role ->  
     <outPort name="OutPort1"> <!-- child element ->  
       …  
     </outPort>  
   </ports> …  
```  
  
 경우는 **UseFullForm** 특성이로 설정 된 true는 추가 중첩 레이어가 도입 되었습니다. 이 레이어는 관계 자체를 나타냅니다. 관계에 속성이 있으면 특성을 true로 설정해야 합니다.  
  
```  
<XmlClassData ElementName="outPort">  
   <DomainClassMoniker Name="OutPort" />  
   <ElementData>  
     <XmlRelationshipData UseFullForm="true" RoleElementName="targets">  
       <DomainRelationshipMoniker Name="Connection" />  
     </XmlRelationshipData>  
   </ElementData>  
 </XmlClassData>  
```  
  
 이 경우 serialize된 파일에는 다음 코드가 포함됩니다.  
  
```  
<outPort name="OutPort1">  <!-- Parent ->  
   <targets>  <!-- role ->  
     <connection sourceRoleName="X">  <!-- relationship link ->  
         <inPortMoniker name="//Component2/InPort1" /> <!-- child ->  
     </connection>  
    </targets>  
  </outPort>  
```  
  
 연결 관계에는 요소 및 특성 이름을 제공하는 자체 XML 클래스 데이터가 있습니다.  
  
 경우는 **OmitElement** 특성이 설정 되어 true 이면 관계 역할 이름이 생략 된 serialize 된 파일을 줄여서 표시 하며 모호 하지 않은 경우 두 개의 클래스에 둘 이상의 관계가 있는 경우. 예를 들어:  
  
```  
<component name="Component3">  
  <!-- only one relationship could get here: ->  
  <outPort name="OutPort1">    
     <targets> …  
```  
  
### <a name="serialization-of-a-domain-specific-language-definition"></a>DSL 정의 serialization  
 DslDefinition.dsl 파일 자체는 serialize된 파일로, DSL 정의를 준수합니다. XML serialization 정의의 몇 가지 예는 다음과 같습니다.  
  
- **Dsl** RootClass 노드이며 다이어그램의 클래스는 합니다. DomainClass, DomainRelationship 및 기타 요소는 `Dsl`에 포함됩니다.  
  
- **클래스** 되는 **RoleElementName** 도메인 특정 언어 및 DomainClass 간 관계.  
  
```  
<Dsl Name="CmptDsl5" …>  
  <Classes>  
    <DomainClass Name="NamedElement" InheritanceModifier="Abstract" …  
```  
  
- **XmlSerializationBehavior** 특성 아래에 포함 되는 `Dsl` 특성을 하지만 **OmitElement** 특성 포함 관계에 대해 설정한. 따라서 `RoleElementName` 특성은 사용되지 않습니다. 반면를 **클래스-데이터** 특성은 합니다 `RoleElementName` 간의 포함 관계의 특성을 **XmlSerializationBehavior** 특성 및 **XmlClassData** 특성입니다.  
  
```  
<Dsl Name="CmptDsl5" …> …  
  <XmlSerializationBehavior Name="ComponentsSerializationBehavior" >  
    <ClassData>  
      <XmlClassData …>…</XmlClassData>  
      <XmlClassData …>…</XmlClassData>  
```  
  
- ConnectorHasDecorators는 `Connector` 및 `Decorator` 간의 포함 관계입니다. `UseFullForm`이 설정되었으므로 Connector 개체로부터의 각 링크에 대한 속성 목록과 함께 관계 이름이 표시됩니다. 그러나 `OmitElement`도 설정되었으므로 `RoleElementName` 내에 포함되는 여러 링크가 `Connector`으로 묶이지 않습니다.  
  
```  
<Connector Name="AssociationLink" …>  
  <ConnectorHasDecorators Position="TargetTop" …>  
    <TextDecorator Name="TargetRoleName"   />  
  </ConnectorHasDecorators>  
  <ConnectorHasDecorators Position="SourceTop" …>  
    <TextDecorator Name="SourceRoleName"   />  
  </ConnectorHasDecorators>  
</Connector>  
```  
  
## <a name="shapes-and-connectors"></a>모양 및 연결선  
 모양 및 연결선 정의는 도메인 클래스에서 특성 및 자식 노드를 상속하며 다음 항목도 상속합니다.  
  
- `Color` 및 `Line``Style` 특성  
  
- **ExposesFillColorAsProperty** 및 여러 유사한 특성. 이러한 부울 특성은 사용자가 해당 속성을 변경할 수 있도록 합니다. 일반적으로 언어 사용자가 다이어그램의 셰이프를 클릭 하면 속성에 표시 되는 **속성** 은 모양이 매핑된 도메인 클래스 인스턴스는 창입니다. `ExposesFillColorAsProperty`를 true로 설정하면 모양 자체의 속성도 표시됩니다.  
  
- **ShapeHasDecorators**. 각 텍스트, 아이콘 또는 확장/축소 Decorator에 대해 이 특성의 인스턴스가 표시됩니다. DslDefinition.dsl 파일에서 `ShapeHasDecorators`는 `UseFullForm`이 true로 설정된 관계입니다.  
  
## <a name="shape-maps"></a>모양 맵  
 모양 맵은 지정한 도메인 클래스 인스턴스가 화면에 나타나는 방식(모양으로 표시됨)을 결정합니다. 모양 및 연결선 맵은 모두 DslDefinition.dsl 파일의 `Diagram` 섹션에 표시됩니다.  
  
 다음 예에서와 같이 `ShapeMap` 요소는 최소한 도메인 클래스의 모니커, 모양의 모니커 및 `ParentElementPath` 요소를 포함합니다.  
  
```  
<ShapeMap>  
  <DomainClassMoniker Name="InPort" />  
  <ParentElementPath>  
    <DomainPath>ComponentHasPorts.Component/!Component</DomainPath>  
  </ParentElementPath>  
  <PortMoniker Name="InPortShape" />  
</ShapeMap>  
```  
  
 `ParentElementPath` 요소의 기본 기능은 같은 개체 클래스가 서로 다른 컨텍스트에서 각기 다른 모양으로 표시되도록 하는 것입니다. 예를 들어 `InPort`도 문서에 포함할 수 있는 경우 `InPort`는 이러한 용도에 맞게 다른 모양으로 표시할 수 있습니다.  
  
 둘째로, 경로는 모양과 부모의 관계를 결정합니다. DslDefinition.dsl 파일에서는 모양 간에 포함 구조가 정의되어 있지 않습니다. 그러므로 모양 맵에서 구조를 유추해야 합니다. 모양의 부모는 부모 요소 경로가 식별하는 도메인 요소에 매핑된 모양입니다. 이 경우 경로는 `InPort`가 속하는 구성 요소를 식별합니다. 다른 모양 맵에서는 Component 클래스가 ComponentShape에 매핑됩니다. 따라서 새 `InPort` 모양은 구성 요소 `ComponentShape`의 자식 모양으로 지정됩니다.  
  
 대신 InPort 모양을 다이어그램에 연결한 경우 부모 요소 경로는 다른 단계를 통해 다이어그램에 매핑된 구성 요소 모델로 이동해야 합니다.  
  
```  
ComponentHasPorts . Component / ! Component /    ComponentModelHasComponents . ComponentModel / ! ComponentModel  
```  
  
 모델 루트에는 모양 맵이 없습니다. 대신 `Class` 요소가 포함된 다이어그램에서 루트를 직접 참조합니다.  
  
```  
<Diagram Name="ComponentDiagram" >  
    <Class>  
      <DomainClassMoniker Name="ComponentModel" />  
    </Class>…  
```  
  
### <a name="decorator-maps"></a>Decorator 맵  
 Decorator 맵은 매핑된 클래스의 속성을 모양의 Decorator와 연결합니다. 속성이 열거된 형식 또는 부울 형식이면 해당 값에 따라 Decorator 표시 여부가 결정될 수 있습니다. 텍스트 Decorator의 경우에는 속성 값이 표시될 수 있으며 사용자가 값을 편집할 수 있습니다.  
  
### <a name="compartment-shape-maps"></a>구획 모양 맵  
 구획 모양 맵은 모양 맵의 하위 형식입니다.  
  
## <a name="connector-maps"></a>연결선 맵  
 최소 연결선 맵은 다음과 같이 연결선과 관계를 참조합니다.  
  
```  
<ConnectorMap>  
  <ConnectorMoniker Name="CommentLink" />  
  <DomainRelationshipMoniker Name="CommentsReferenceComponents" />  
</ConnectorMap>  
```  
  
 연결선 맵은 Decorator 맵을 포함할 수도 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [도메인 특정 언어 도구 용어집](https://msdn.microsoft.com/ca5e84cb-a315-465c-be24-76aa3df276aa)   
 [도메인 특정 언어를 정의 하는 방법](../modeling/how-to-define-a-domain-specific-language.md)   
 [모델, 클래스 및 관계 이해](../modeling/understanding-models-classes-and-relationships.md)

---
title: DSL에서 표준 메뉴 명령 수정
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- .vsct files, adding commands to a domain-specific language
- Domain-Specific Language, adding custom commands
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 466df3030793603319cf73085910a164fd222e29
ms.sourcegitcommit: 748d9cd7328a30f8c80ce42198a94a4b5e869f26
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2019
ms.locfileid: "67890604"
---
# <a name="how-to-modify-a-standard-menu-command-in-a-domain-specific-language"></a>방법: 도메인 특정 언어에서 표준 메뉴 명령 수정

DSL에서 자동으로 정의되는 일부 표준 명령의 동작을 수정할 수 있습니다. 예를 들어, 수정할 수 있습니다 **잘라내기** 중요 한 정보가 제외 되도록 합니다. 이렇게 하려면 명령 집합 클래스에서 메서드를 재정의합니다. 이러한 클래스는 DslPackage 프로젝트의 CommandSet.cs 파일에서 정의되며 <xref:Microsoft.VisualStudio.Modeling.Shell.CommandSet>에서 파생됩니다.

> [!NOTE]
> 메뉴 명령을 직접 만들려는 경우 참조 [방법: 바로 가기 메뉴에 명령을 추가](../modeling/how-to-add-a-command-to-the-shortcut-menu.md)합니다.

## <a name="what-commands-can-you-modify"></a>수정할 수 있는 명령

### <a name="to-discover-what-commands-you-can-modify"></a>수정할 수 있는 명령을 파악하려면

1. 에 `DslPackage` 프로젝트를 열고 `GeneratedCode\CommandSet.cs`합니다. 이 C# 파일의 보조 파일로 솔루션 탐색기에서 찾을 수 있습니다 `CommandSet.tt`합니다.

2. 사용 하 여 해당 이름 끝이이 파일에서 클래스를 찾을 "`CommandSet`", 예를 들어 `Language1CommandSet` 고 `Language1ClipboardCommandSet`입니다.

3. 각 명령 집합 클래스에서 "`override`"와 공백을 차례로 입력합니다. 그러면 IntelliSense에서 재정의할 수 있는 메서드 목록을 표시합니다. 각 명령에는 이름이 "`ProcessOnStatus`" 및 "`ProcessOnMenu`"로 시작하는 메서드 쌍이 있습니다.

4. 수정할 명령이 포함된 명령 집합 클래스를 확인합니다.

5. 편집 내용을 저장하지 않고 파일을 닫습니다.

    > [!NOTE]
    > 일반적으로는 생성된 파일을 편집하면 안 됩니다. 다음 번에 파일을 생성하면 편집 내용이 손실됩니다.

## <a name="extend-the-appropriate-command-set-class"></a>해당 명령 집합 클래스 확장

명령 집합 클래스의 partial 선언이 포함된 새 파일을 만듭니다.

### <a name="to-extend-the-command-set-class"></a>명령 집합 클래스를 확장하려면

1. 솔루션 탐색기의 DslPackage 프로젝트에서 GeneratedCode 폴더를 열고 CommandSet.tt를 확인하여 생성된 CommandSet.cs 파일을 엽니다. 이 파일에 정의된 첫 번째 클래스의 이름과 네임스페이스를 확인합니다. 예를 들어 다음과 같은 코드가 표시될 수 있습니다.

     `namespace Company.Language1`

     `{ ...  internal partial class Language1CommandSet : ...`

2. **DslPackage**, 라는 폴더를 만듭니다 **사용자 지정 코드**합니다. 이 폴더에서 이라는 새 클래스 파일을 만듭니다 `CommandSet.cs`합니다.

3. 새 파일에 생성된 partial 클래스와 이름 및 네임스페이스가 같은 partial 선언을 작성합니다. 예를 들어:

    ```csharp
    using System;
    using System.Collections.Generic;
    using System.ComponentModel.Design;
    namespace Company.Language1 /* Make sure this is correct */
    { internal partial class Language1CommandSet { ...
    ```

    > [!NOTE]
    > 클래스 파일 템플릿을 사용 하는 새 파일을 만드는 경우 네임 스페이스 및 클래스 이름을 모두 수정 해야 합니다.

## <a name="override-the-command-methods"></a>명령 메서드 재정의

대부분의 명령에는 두 연결된 방법이 있습니다. 이름 사용 하 여 메서드 같은 `ProcessOnStatus`... 명령이 표시 되 고 사용할 수 있어야 하는지 여부를 결정 합니다. 이 메서드는 사용자가 다이어그램을 마우스 오른쪽 단추로 클릭할 때마다 호출되고 빠르게 실행되며 아무것도 변경하지 않아야 합니다. `ProcessOnMenu`... 사용자 명령을 클릭 하 고 명령의 기능을 수행 해야 하는 경우 호출 됩니다. 이 두 메서드 중 하나 또는 둘 다를 재정의할 수 있습니다.

### <a name="to-change-when-the-command-appears-on-a-menu"></a>메뉴에 명령이 표시되는 경우를 변경하려면

... Processonstatus 메서드. 이 메서드는 해당 MenuCommand 매개 변수의 Visible 및 Enabled 속성을 설정합니다. 일반적으로 명령은 this.CurrentSelection을 확인하여 명령이 선택한 요소에 적용되는지 여부를 결정하며, 이러한 요소의 속성을 확인하여 현재 상태에 명령을 적용할 수 있는지 여부도 결정할 수 있습니다.

일반적으로는 선택한 요소에 따라 Visible 속성이 결정되어야 합니다. 명령이 메뉴에서 표시되는 색(검은색 또는 회색)을 결정하는 Enabled 속성은 현재 선택 상태에 따라 결정되어야 합니다.

다음 예에서는 사용자가 둘 이상의 모양을 선택하면 Delete 메뉴 항목을 사용하지 않도록 설정합니다.

> [!NOTE]
> 이 메서드는 키 입력을 통해 명령을 사용할 수 있는지 여부에는 영향을 주지 않습니다. 예를 들어 Delete 메뉴 항목을 사용하지 않도록 설정해도 Delete 키를 통해 명령을 호출할 수는 있습니다.

```csharp
/// <summary>
/// Called when user right-clicks on the diagram or clicks the Edit menu.
/// </summary>
/// <param name="command">Set Visible and Enabled properties.</param>
protected override void ProcessOnStatusDeleteCommand (MenuCommand command)
{
  // Default settings from the base method.
  base.ProcessOnStatusDeleteCommand(command);
  if (this.CurrentSelection.Count > 1)
  {
    // If user has selected more than one item, Delete is greyed out.
    command.Enabled = false;
  }
}
```

일일이 확인하기 어려운 모든 사례와 설정을 처리하려면 기본 메서드를 먼저 호출하는 것이 좋습니다.

ProcessOnStatus 메서드는 Store에서 요소를 작성, 삭제 또는 업데이트하지 않습니다.

### <a name="to-change-the-behavior-of-the-command"></a>명령의 동작을 변경하려면

... Processonmenu 메서드. 다음 예에서는 사용자가 Delete 키를 사용하더라도 한 번에 요소를 둘 이상 삭제하지 못하도록 지정합니다.

```csharp
/// <summary>
/// Called when user presses Delete key
/// or clicks the Delete command on a menu.
/// </summary>
protected override void ProcessOnMenuDeleteCommand()
{
  // Allow users to delete only one thing at a time.
  if (this.CurrentSelection.Count <= 1)
  {
    base.ProcessOnMenuDeleteCommand();
  }
}
```

코드가 Store에서 요소 또는 링크 작성, 삭제, 업데이트 등의 변경을 수행하는 경우에는 트랜잭션 내에서 해당 변경이 수행되도록 해야 합니다. 자세한 내용은 [모델 요소 만들기 및 업데이트 하는 방법을](../modeling/how-to-modify-a-standard-menu-command-in-a-domain-specific-language.md)합니다.

### <a name="write-the-code-of-the-methods"></a>메서드의 코드를 작성 합니다.

이러한 메서드 내에서는 다음 코드 조각이 유용하게 사용되는 경우가 많습니다.

- `this.CurrentSelection`. 사용자가 마우스 오른쪽 단추로 클릭한 모양은 항상 이 모양 및 연결선 목록에 포함됩니다. 사용자가 다이어그램의 빈 부분을 클릭하는 경우의 목록 멤버는 Diagram뿐입니다.

- `this.IsDiagramSelected()` - `true` 사용자가 다이어그램의 빈 부분입니다.

- `this.IsCurrentDiagramEmpty()`

- `this.IsSingleSelection()` - 사용자가 여러 모양을 선택하지 않은 경우입니다.

- `this.SingleSelection` - 사용자가 마우스 오른쪽 단추로 클릭한 모양이나 다이어그램입니다.

- `shape.ModelElement as MyLanguageElement` - 모양이 나타내는 모델 요소입니다.

개체 및 링크를 만드는 방법에 대 한 요소를 이동 하는 방법에 대 한 자세한 내용은 참조 하세요 [탐색 및 업데이트 프로그램 코드에서 모델](../modeling/navigating-and-updating-a-model-in-program-code.md)합니다.

## <a name="see-also"></a>참고자료

- <xref:System.ComponentModel.Design.MenuCommand>
- [도메인별 언어를 사용자 지정하는 코드 작성](../modeling/writing-code-to-customise-a-domain-specific-language.md)
- [방법: 바로 가기 메뉴에 명령 추가](../modeling/how-to-add-a-command-to-the-shortcut-menu.md)
- [VSPackage에서 사용자 인터페이스 요소를 추가하는 방법](../extensibility/internals/how-vspackages-add-user-interface-elements.md)
- [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML 스키마 참조](../extensibility/vsct-xml-schema-reference.md)
- [-VMSDK 회로 다이어그램 샘플입니다. 광범위 한 DSL 사용자 지정](https://code.msdn.microsoft.com/Visualization-Modeling-SDK-763778e8)

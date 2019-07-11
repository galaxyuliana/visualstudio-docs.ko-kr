---
title: XAML 디자이너 확장성 마이그레이션
ms.date: 07/09/2019
ms.topic: conceptual
author: lutzroeder
ms.author: lutzr
manager: jillfra
dev_langs:
- csharp
- vb
monikerRange: vs-2019
ms.openlocfilehash: 52bc8a6a0097d255891f4b6111a27bff85091bec
ms.sourcegitcommit: 208395bc122f8d3dae3f5e5960c42981cc368310
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67784486"
---
# <a name="xaml-designer-extensibility-migration"></a>XAML 디자이너 확장성 마이그레이션

Visual Studio 2019 공개 미리 보기로 16.1 버전부터 XAML 디자이너를 사용 하는 두 개의 다른 아키텍처를 지원 합니다: 디자이너 격리 아키텍처 및 최신 노출 격리 아키텍처입니다. 이 아키텍처 전환은.NET Framework 프로세스에서 호스팅할 수 없는 대상 런타임을 지 원하는 데 필요 합니다. 타사 확장성 모델에 주요 변경 내용 소개 노출 격리 아키텍처로 이동 합니다. 이 문서에 변경 내용을 간략하게 설명합니다.

**디자이너 격리** .NET Framework를 대상으로 하는 프로젝트에 WPF 디자이너에서 사용 되 고 지 원하는 *. design.dll* 확장 합니다. 사용자 코드, 컨트롤 라이브러리 및 제 3 자 확장이 외부 프로세스에서 로드 됩니다 (*XDesProc.exe*) 실제 디자이너 코드 및 디자이너 패널 함께 합니다.

**격리 화면** UWP 디자이너에서 사용 됩니다. 또한.NET Core를 대상으로 하는 프로젝트에 대 한 WPF 디자이너에서 사용 됩니다. 화면 격리에만 사용자 코드 및 컨트롤 라이브러리에에서 로드 된 별도 프로세스 디자이너 및 해당 패널 Visual Studio 프로세스에 로드 하는 동안 (*DevEnv.exe*). 사용자 코드 및 컨트롤 라이브러리를 실행 하는 데 사용 된 런타임 실제 디자이너와 타사 확장성 코드에 대 한.NET Framework에서 사용 되는 다릅니다.

![확장성-마이그레이션-아키텍처](media/xaml-designer-extensibility-migration-architecture.png)

이러한 아키텍처 전환으로 인해 제 3 자 확장이 더 이상 타사 컨트롤 라이브러리와 동일한 프로세스에 로드 됩니다. 더 이상 확장 컨트롤 라이브러리에 직접 종속 되어 하거나 런타임 개체에 직접 액세스할 수 없습니다. 사용 하 여 디자이너 격리 아키텍처에 대 한 이전에 작성 된 확장을 *Microsoft.Windows.Extensibility.dll* API를 노출 격리 아키텍처를 사용 하는 새로운 방법으로 마이그레이션해야 합니다. 실제로 새 확장성 API 어셈블리에 대해 컴파일할 수 기존 확장 해야 합니다. 런타임에 컨트롤에 대 한 액세스를 통해 형식 [typeof](/dotnet/csharp/language-reference/keywords/typeof) 또는 런타임 인스턴스를 대체 하거나 컨트롤 라이브러리는 이제 다른 프로세스에서 로드 되므로 제거 해야 합니다.

## <a name="new-extensibility-api-assemblies"></a>새 확장성 API 어셈블리

새 확장성 API 어셈블리 기존 확장성 API 어셈블리와 유사 하지만 구분할 수 있도록 다른 이름 지정 체계를 따릅니다. 마찬가지로, 네임 스페이스 이름을 새 어셈블리 이름을 반영 하도록 변경 되었습니다.

| 디자이너 격리 API 어셈블리            | Surface 격리 API 어셈블리                       |
|:------------------------------------------ |:---------------------------------------------------- |
| Microsoft.Windows.Design.Extensibility.dll | Microsoft.VisualStudio.DesignTools.Extensibility.dll |
| Microsoft.Windows.Design.Interaction.dll   | Microsoft.VisualStudio.DesignTools.Interaction.dll   |

## <a name="new-file-extension-and-discovery"></a>새 파일 확장명 및 검색

사용 하는 대신 합니다 *. design.dll* 파일 확장명을 사용 하 여 확장을 검색할 수는 새 화면을 *. designtools.dll* 파일 확장명입니다. *. design.dll* 하 고 *. designtools.dll* 확장 동일한 존재할 수 있습니다 *디자인* 하위 폴더입니다.

실제 대상 런타임 (.NET Core 또는 UWP)에 대 한 타사 컨트롤 라이브러리 컴파일되는 동안 합니다 *. designtools.dll* 확장 항상.NET Framework 어셈블리로 컴파일됩니다.

## <a name="decouple-attribute-tables-from-runtime-types"></a>런타임 형식에서 특성 테이블 분리

실제 컨트롤 라이브러리에 의존 하는 확장에 대 한 노출 격리 확장성 모델을 허용 하지 않습니다 하 고 확장 컨트롤 라이브러리에서 형식을 참조할 수 없습니다 따라서 키를 누릅니다. 예를 들어 *MyLibrary.designtools.dll* 대 한 종속성이 없어야 *MyLibrary.dll*합니다.

이러한 종속성 특성 테이블을 통해 형식에 대 한 메타 데이터를 등록 하는 경우 가장 많았습니다. 컨트롤 라이브러리를 참조 하는 확장 코드를 통해 직접 형식 [typeof](/dotnet/csharp/language-reference/keywords/typeof) ([GetType](/dotnet/visual-basic/language-reference/operators/gettype-operator) Visual basic에서)은 문자열 기반 형식 이름을 사용 하 여 새 Api에서 대체 됩니다.

```csharp
using Microsoft.VisualStudio.DesignTools.Extensibility.Metadata;
using Microsoft.VisualStudio.DesignTools.Extensibility.Features;
using Microsoft.VisualStudio.DesignTools.Extensibility.Model;

[assembly: ProvideMetadata(typeof(AttributeTableProvider))]

public class AttributeTableProvider : IProvideAttributeTable
{
  public AttributeTable AttributeTable
  {
    get
    {
      AttributeTableBuilder builder = new AttributeTableBuilder();
      builder.AddCustomAttributes("MyLibrary.MyControl", new DescriptionAttribute(Strings.MyControlDescription);
      builder.AddCustomAttributes("MyLibrary.MyControl", new FeatureAttribute(typeof(MyControlDefaultInitializer));
      return builder.CreateTable();
    }
  }
}
```

```vb
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Metadata
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Features
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Model

<Assembly: ProvideMetadata(GetType(AttributeTableProvider))>

Public Class AttributeTableProvider
    Implements IProvideAttributeTable

    Public ReadOnly Property AttributeTable As AttributeTable Implements IProvideAttributeTable.AttributeTable
        Get
            Dim builder As New AttributeTableBuilder
            builder.AddCustomAttributes("MyLibrary.MyControl", New DescriptionAttribute(Strings.MyControlDescription))
            builder.AddCustomAttributes("MyLibrary.MyControl", New FeatureAttribute(GetType(MyControlDefaultInitializer)))
            Return builder.CreateTable()
        End Get
    End Property
End Class
```

## <a name="feature-providers-and-model-api"></a>기능 공급자 및 모델 API

기능 공급자 확장 프로그램 어셈블리에서 구현 되 고 Visual Studio 프로세스에 로드 합니다. `FeatureAttribute` 기능 공급자 형식을 사용 하 여 직접 참조는 계속 [typeof](/dotnet/csharp/language-reference/keywords/typeof)합니다.

되기 때문에 이제 기능 공급자의 실제 런타임 코드 및 컨트롤 라이브러리에서 다른 프로세스에서 로드 되어, 더 이상 런타임 개체에 직접 액세스할 수 없습니다. 대신 이러한 모든 상호 작용은 해당 모델 기반 Api를 사용 하도록 변환 되어야 합니다. 모델 API가 업데이트 되 고에 대 한 액세스 <xref:System.Type> 또는 <xref:System.Object> 는 더 이상 사용할 수 또는 바뀌었습니다 `TypeIdentifier` 및 `TypeDefinition`합니다.

`TypeIdentifier` 형식을 식별 하는 어셈블리 이름 없이 문자열을 나타냅니다. `TypeIdenfifier` 로 확인 될 수는 `TypeDefinition` 유형에 대 한 추가 정보를 쿼리할 수 있습니다. `TypeDefinition` 확장 프로그램 코드에서 인스턴스를 캐시할 수 없습니다.

```csharp
TypeDefinition type = ModelFactory.ResolveType(
    item.Context, new TypeIdentifier("MyLibrary.MyControl"));
TypeDefinition buttonType = ModelFactory.ResolveType(
    item.Context, new TypeIdentifier("System.Windows.Controls.Button"));
if (type != null && buttonType != type.IsSubclassOf(buttonType))
{
}
```

```vb
Dim type As TypeDefinition = ModelFactory.ResolveType(
    item.Context, New TypeIdentifier("MyLibrary.MyControl"))
Dim buttonType As TypeDefinition = ModelFactory.ResolveType(
    item.Context, New TypeIdentifier("System.Windows.Controls.Button"))
If type?.IsSubclassOf(buttonType) Then

End If
```

Api 노출 격리 확장성 API 집합에서 제거 합니다.

* `ModelFactory.CreateItem(EditingContext context, object item)`
* `ViewItem.PlatformObject`
* `ModelProperty.DefaultValue`

사용 하는 Api `TypeIdentifier` 대신 <xref:System.Type>:

* `ModelFactory.CreateItem(EditingContext context, Type itemType, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, Type itemType, CreateOptions options, params object[] arguments)`
* `ModelFactory.CreateStaticMemberItem(EditingContext context, Type type, string memberName)`
* `ViewItem.ItemType`
* `ModelEvent.EventType`
* `ModelEvent.IsEventOfType(Type type)`
* `ModeItem.IsItemOfType(Type type)`
* `ModelParent.CanParent(EditingContext context, ModelItem parent, Type childType)`
* `ModelParent.FindParent(EditingContext context, Type childType, ModelItem startingItem)`
* `ModelParent.FindParent(Type childType, GestureData gestureData)`
* `ModelProperty.IsPropertyOfType(Type type)`
* `ParentAdpater.CanParent(ModelItem parent, Type childType)`
* `ParentAdapter.RedirectParent(ModelItem parent, Type childType)`

사용 하는 Api `TypeIdentifier` 대신 <xref:System.Type> 생성자 인수를 더 이상 지원 합니다.

* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, params object[] arguments)`
* `ModelFactory.CreateItem(EditingContext context, TypeIdentifier typeIdentifier, CreateOptions options, params object[] arguments)`

사용 하는 Api `TypeDefinition` 대신 <xref:System.Type>:

* `ModelFactory.ResolveType(EditingContext context, TypeIdentifier typeIdentifier)`
* `ValueTranslationService.GetProperties(Type itemType)`
* `ValueTranslationService.HasValueTranslation(Type itemType, PropertyIdentifier identifier)`
* `ValueTranslationService.TranslatePropertyValue(Type itemType, ModelItem item, PropertyIdentifier identifier, object value)`
* `ModelService.Find(ModelItem startingItem, Type type)`
* `ModelService.Find(ModelItem startingItem, Predicate<Type> match)`
* `ModelItem.ItemType`
* `ModelProperty.AttachedOwnerType`
* `ModelProperty.PropertyType`
* `FeatureManager.CreateFeatureProviders(Type featureProviderType, Type type)`
* `FeatureManager.CreateFeatureProviders(Type featureProviderType, Type type, Predicate<Type> match)`
* `FeatureManager.InitializeFeatures(Type type)`
* `FeatureManager.GetCustomAttributes(Type type, Type attributeType)`
* `AdapterService.GetAdapter<TAdapterType>(Type itemType)`
* `AdapterService.GetAdapter(Type adapterType, Type itemType)`

사용 하는 Api `ModelItem` 대신 <xref:System.Object>:

* `ModelItemCollection.Insert(int index, object value)`
* `ModelItemCollection.Remove(object value)`
* `ModelItemDictionary.Add(object key, object value)`
* `ModelItemDictionary.ContainsKey(object key)`
* `ModelItemDictionary.Remove(object key)`
* `ModelItemDictionary.TryGetValue(object key, out ModelItem value)`

같은 기본 형식이 알려진 `Int32`, `String`, 또는 `Thickness` .NET Framework 인스턴스로 모델 API에 전달 될 수 있으며 대상 런타임 프로세스에서 해당 개체로 변환 됩니다. 예:

```csharp
using Microsoft.VisualStudio.DesignTools.Extensibility.Features;
using Microsoft.VisualStudio.DesignTools.Extensibility.Model;

public class MyControlDefaultInitializer : DefaultInitializer
{
  public override void InitializeDefaults(ModelItem item)
  {
    item.Properties["Width"].SetValue(800d);
    base.InitializeDefaults(item);
  }
}
```

```vb
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Features
Imports Microsoft.VisualStudio.DesignTools.Extensibility.Model

Public Class MyControlDefaultInitializer
    Inherits DefaultInitializer

    Public Overrides Sub InitializeDefaults(item As ModelItem)
        item.Properties!Width.SetValue(800.0)
        MyBase.InitializeDefaults(item)
    End Sub
End Class
```

## <a name="limited-support-for-designdll-extensions"></a>제한적으로 지원 합니다. design.dll 확장

있는 경우 *. designtools.dll* 확장 컨트롤 라이브러리에 대 한 검색, 첫 번째 및 검색에 대 한 로드 *. design.dll* 확장을 건너뜁니다.

없으면 *. designtools.dll* extensions가 있지만 *. design.dll* 확장이, XAML 언어 서비스를 지원 하기 위해 특성 테이블 정보를 추출 하려면이 어셈블리를 로드 하려고 합니다. 기본 편집기 및 속성 검사자 시나리오입니다. 이 메커니즘은 범위에서 제한 됩니다. 기능 공급자를 실행 하도록 격리 디자이너 확장의 로드를 허용 하지 않지만 기존 WPF 컨트롤 라이브러리에 대 한 기본 지원을 제공할 수 있습니다.

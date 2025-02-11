---
title: 디버깅 하는 동안 XAML 속성 검사 | Microsoft Docs
ms.date: 03/06/2017
ms.topic: conceptual
ms.assetid: 390edde4-7b8d-4c89-8d69-55106b7e6b11
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- uwp
ms.openlocfilehash: d5b04a64ea75458d23e64e83a405a103ae70a100
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62906068"
---
# <a name="inspect-xaml-properties-while-debugging"></a>디버그하는 동안 XAML 속성 검사
**라이브 시각적 트리** 및 **라이브 속성 탐색기**를 사용하여 실행 중인 XAML 코드를 실시간으로 볼 수 있습니다. 이러한 도구는 실행 중인 XAML 애플리케이션의 UI 요소에 대한 트리 뷰를 제공하고 선택한 UI 요소의 런타임 속성을 보여 줍니다.

다음 구성에서 이러한 도구를 사용할 수 있습니다.

|앱 유형|운영 체제 및 도구|
|-----------------|--------------------------------|
|Windows Presentation Foundation(4.0 이상) 애플리케이션|Windows 7 이상|
|유니버설 Windows 앱|Windows 10 이상에서 사용 하 여는 [Windows 10 SDK](https://dev.windows.com/en-us/downloads/windows-10-sdk)|

## <a name="looking-at-elements-in-the-live-visual-tree"></a>라이브 시각적 트리의 요소 보기
목록 보기 및 단추가 있는 매우 간단한 WPF 애플리케이션을 시작하겠습니다. 단추를 클릭할 때마다 다른 항목이 목록에 추가됩니다. 짝수 번호 항목은 회색으로 표시되고 홀수 번호 항목은 노란색으로 표시됩니다.

새 C# WPF 애플리케이션을 만듭니다(파일 > 새로 만들기 > 프로젝트를 선택한 다음, C#을 선택하고 WPF 애플리케이션 찾기). **TestXAML**로 이름을 지정합니다.

다음과 같이 MainWindow.xaml을 변경합니다.

```xaml
<Window x:Class="TestXAML.MainWindow"
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    xmlns:d="http://schemas.microsoft.com/expression/blend/2008"
    xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006"
    xmlns:local="clr-namespace:TestXAML"
    mc:Ignorable="d"
    Title="MainWindow" Height="350" Width="525">
    <Grid>
        <Button x:Name="button" Background="LightBlue" Content="Add Item" HorizontalAlignment="Left" Margin="216,206,0,0" VerticalAlignment="Top" Width="75" Click="button_Click"/>
        <ListBox x:Name="listBox" HorizontalAlignment="Left" Height="100" VerticalAlignment="Top" Width="100" Margin="205,80,0,0"/>
    </Grid>
</Window>
```

MainWindow.xaml.cs 파일에 다음 명령 처리기를 추가합니다.

```csharp
int count;

private void button_Click(object sender, RoutedEventArgs e)
{
    ListBoxItem item = new ListBoxItem();
    item.Content = "Item" + ++count;
    if (count % 2 == 0)
    {
        item.Background = Brushes.LightGray;
    }
    else
    {
        item.Background = Brushes.LightYellow;
    }
    listBox.Items.Add(item);
}
```

프로젝트를 빌드하고 디버깅을 시작합니다. (빌드 구성은 릴리스가 아닌 디버그여야 합니다. 빌드 구성에 대한 자세한 내용은 [빌드 구성 이해](../ide/understanding-build-configurations.md)를 참조하세요.)

창이 표시되면 **항목 추가** 단추를 몇 번 클릭합니다. 다음과 같이 표시되어야 합니다.

![앱의 주 창이](../debugger/media/livevisualtree-app.png "LiveVIsualTree 앱")

이제 **라이브 시각적 트리** 창(**디버그 > 창 > 라이브 시각적 트리** 또는 IDE의 왼쪽을 따라 찾기)을 엽니다. 이 창과 **라이브 속성** 창을 나란히 볼 수 있도록 이 창을 도킹 위치에서 벗어나도록 끕니다. **라이브 시각적 트리** 창에서 **ContentPresenter** 노드를 확장합니다. 단추와 목록 상자에 대한 노드가 있어야 합니다. 목록 상자와 **ScrollContentPresenter** 및 **ItemsPresenter**를 차례로 확장하여 목록 상자 항목을 찾습니다. 창이 다음과 같이 표시되어야 합니다.

![라이브 시각적 트리의 Listboxitem](../debugger/media/livevisualtree-listboxitems.png "LiveVisualTree Listboxitem")

애플리케이션 창으로 다시 이동하고 더 많은 항목을 추가합니다. 더 많은 목록 상자 항목이 **라이브 시각적 트리**에 나타나야 합니다.

이제 목록 상자 항목 중 하나의 속성을 살펴보겠습니다. **라이브 시각적 트리**의 첫 번째 목록 상자 항목을 선택하고 도구 모음에서 **속성 표시** 아이콘을 클릭합니다. **라이브 속성 탐색기**가 표시됩니다. **콘텐츠** 필드는 "Item1"이고 **배경** 필드는 **#FFFFFFE0**(연한 노랑)입니다. **라이브 시각적 트리**로 돌아가서 두 번째 목록 상자 항목을 선택합니다. **라이브 속성 탐색기**에서 **콘텐츠** 필드는 "Item2"로, **배경** 필드는 **#FFD3D3D3**(밝은 회색)으로 표시되어야 합니다.

XAML의 실제 구조에는 직접적으로 관련이 없는 많은 요소가 있습니다. 코드를 잘 모르면 트리에서 필요한 항목을 찾기가 어려울 수 있습니다. 따라서 **라이브 시각적 트리**에는 검사하려는 요소를 찾는 데 도움이 되는 애플리케이션 UI를 사용할 수 있는 몇 가지 방법이 있습니다.

**실행 중인 애플리케이션에서 선택을 사용합니다**. **라이브 시각적 트리** 도구 모음의 가장 왼쪽에 있는 단추를 선택하면 이 모드를 사용할 수 있습니다. 이 모드를 켜면 애플리케이션에서 UI 요소를 선택할 수 있고 **라이브 시각적 트리**(및 **라이브 속성 뷰어**)가 이 요소 및 해당 속성에 해당하는 트리에 노드를 표시하도록 자동으로 업데이트됩니다.

**실행 중인 애플리케이션에 레이아웃 표시기를 표시합니다**. 선택 사용 단추 바로 오른쪽에 있는 단추를 선택하면 이 모드를 사용할 수 있습니다. **레이아웃 표시기 표시**를 켜면 애플리케이션 창에 선택한 개체의 범위를 따라 가로 및 세로줄이 표시됩니다. 따라서 여백을 표시하는 사각형뿐만 아니라 어떤 항목이 정렬되는지 확인할 수 있습니다. 예를 들어 **선택 사용** 및 **레이아웃 표시**를 모두 켜고 애플리케이션에서 **항목 추가** 텍스트 블록을 선택합니다. **라이브 시각적 트리**에 텍스트 블록 노드가 표시되고 **라이브 속성 뷰어**에 텍스트 블록 속성이 표시되어야 합니다. 또한 텍스트 블록의 범위에는 가로 및 세로줄이 표시되어야 합니다.

![Displaylayout의 Livepropertyviewer](../debugger/media/livevisualtreelivepropertyviewer-displaylayout.png "LiveVisualTreeLivePropertyViewer DisplayLayout")

**선택 미리 보기**. 라이브 시각적 트리 도구 모음의 왼쪽에서 세 번째 단추를 선택하면 이 모드를 사용할 수 있습니다. 이 모드에서는 애플리케이션의 소스 코드에 액세스할 수 있는 경우 요소가 선언된 XAML을 보여 줍니다. **선택 사용** 및 **선택 미리 보기**를 선택한 다음, 테스트 애플리케이션에서 단추를 선택합니다. Visual Studio에서 MainWindow.xaml 파일이 열리고 커서가 단추가 정의된 줄에 위치합니다.

## <a name="using-xaml-tools-with-running-applications"></a>애플리케이션이 실행 중인 상태에서 XAML 도구를 사용
소스 코드가 없는 경우 이러한 XAML 도구를 사용할 수 있습니다. 실행 중인 XAML 애플리케이션에 연결하면 해당 애플리케이션의 UI 요소에서도 **라이브 시각적 트리**를 사용할 수 있습니다. 다음은 이전에 사용한 동일한 WPF 테스트 애플리케이션을 사용하는 예제입니다.

1. 릴리스 구성에서 **TestXaml** 애플리케이션을 시작합니다. **디버그** 구성으로 실행 중인 프로세스에는 연결할 수 없습니다.

2. Visual Studio의 두 번째 인스턴스를 열고 **디버그 > 프로세스에 연결**을 클릭합니다. 사용 가능한 프로세스 목록에서 **TestXaml.exe**를 찾고 **연결**을 클릭합니다.

3. 애플리케이션이 실행되기 시작합니다.

4. Visual Studio의 두 번째 인스턴스에서 **라이브 시각적 트리**(**디버그 > 창 > 라이브 시각적 트리**)를 엽니다. **TestXaml** UI 요소가 표시되어야 하고 애플리케이션을 직접 디버그하는 동안 했던 것처럼 해당 요소를 조작할 수 있어야 합니다.

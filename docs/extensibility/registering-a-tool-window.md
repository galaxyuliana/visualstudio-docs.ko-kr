---
title: 도구 창을 등록 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- tool windows, registering managed
- tool windows, registering
ms.assetid: 8c8c4a24-3da4-497b-9db2-0ddd7cfbfdd2
author: gregvanl
ms.author: gregvanl
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 8ef5cc84ea1fdce8e297d8b5bff6636065b3d044
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62805786"
---
# <a name="register-a-tool-window"></a>도구 창 등록
도구 창을 사용 하 여 등록할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 고 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowVisibilityAttribute>입니다.

## <a name="example"></a>예제

```csharp

[ProvideToolWindow(typeof(PersistedWindowPane), Style = MsVsShell.VsDockStyle.Tabbed, Window = "3ae79031-e1bc-11d0-8f78-00a0c9110057")]
[ProvideToolWindow(typeof(DynamicWindowPane), PositionX=250, PositionY=250, Width=160, Height=180, Transient=true)]
[ProvideToolWindowVisibility(typeof(DynamicWindowPane), /*UICONTEXT_SolutionExists*/"f1536ef8-92ec-443c-9ed7-fdadf150da82")]
[ProvideMenuResource(1000, 1)]
[PackageRegistration(UseManagedResourcesOnly = true)]
[Guid("01069CDD-95CE-4620-AC21-DDFF6C57F012")]
public class PackageToolWindow : Package
{
```

 위의 코드에서의 <xref:Microsoft.VisualStudio.Shell.ProvideToolWindowAttribute> 등록 합니다 `PersistedWindowPane` 및 `DynamicWindowPane` Visual Studio를 사용 하 여 windows 도구입니다. 지속형된 도구 창을 도킹 하 고 사용 하 여 탭은 **솔루션 탐색기**, 고 동적 창 시작 위치 및 크기는 기본 제공 됩니다. 시작 시에 생성 되지 않도록 나타냅니다 동적 창 일시적인 수행 됩니다. 기록를 `DontForceCreate` 값을 `ToolWindows` 시스템 레지스트리에 키입니다. 자세한 내용은 [도구 창 표시 구성](../extensibility/tool-window-display-configuration.md)합니다.

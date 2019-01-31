---
title: 개체의 사용자 지정 뷰 만들기 | Microsoft Docs
ms.date: 01/08/2019
ms.topic: conceptual
f1_keywords:
- vs.debug.data.elements
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- data types, custom
- custom data types
- managed code, custom data types
- autoexp.dat file
- mcee_cs.dat file
- debugger, expanding data types
- mcee_mc.dat file
ms.assetid: 9969e9b2-9008-4729-8a14-0d6deaa61576
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- dotnet
ms.openlocfilehash: 57480eff4e2ad6e6c33008be6f1bbc2a2f332432
ms.sourcegitcommit: 2193323efc608118e0ce6f6b2ff532f158245d56
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 01/25/2019
ms.locfileid: "55015097"
---
# <a name="create-custom-views-of-objects-c-visual-basic-c"></a>개체의 사용자 지정 뷰 만들기 (C#, Visual Basic, c + +)
Visual Studio에서 디버거 변수 창에 데이터 형식이 표시되는 방식을 사용자 지정할 수 있습니다.  

## <a name="native-code"></a>네이티브 코드

C + + 코드를 추가할 수 있습니다 Natvis 프레임 워크를 사용 하 여 사용자 지정 데이터 형식 확장에 설명 된 대로 [디버거에서 네이티브 개체의 사용자 지정 뷰 만들기](/visualstudio/debugger/create-custom-views-of-native-objects)합니다. C + + /cli 코드를 사용할 수도 있습니다이 문서에서 여기에 설명 된 특성입니다.

## <a name="attributes"></a>특성

C#, Visual Basic 및 c + + (C + + CLI 코드에만 해당)를 사용 하 여 사용자 지정 데이터에 대 한 확장을 추가할 수 있습니다 <xref:System.Diagnostics.DebuggerTypeProxyAttribute>, <xref:System.Diagnostics.DebuggerDisplayAttribute>, 및 <xref:System.Diagnostics.DebuggerBrowsableAttribute>합니다.  
  
[!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 코드에서 Visual Basic은 DebuggerBrowsable 특성을 지원하지 않습니다. 최신 버전의 .NET Framework에서는 이러한 제한 사항이 제거되었습니다.    

## <a name="visualizers"></a>시각화 도우미

시각화 도우미를 작성하여 관리되는 데이터 형식을 표시할 수 있습니다. 자세한 내용은 [방법: 시각화 도우미 작성](/visualstudio/debugger/create-custom-visualizers-of-data)을 참조하세요.
  
## <a name="see-also"></a>참고 항목  
 [DebuggerTypeProxy 특성 사용](../debugger/using-debuggertypeproxy-attribute.md)   
 [DebuggerDisplay 특성 사용](../debugger/using-the-debuggerdisplay-attribute.md)   
 [조사식 및 간략한 조사식 창](../debugger/watch-and-quickwatch-windows.md)   
 [디버거 표시 특성을 사용하여 디버깅 향상](/dotnet/framework/debug-trace-profile/enhancing-debugging-with-the-debugger-display-attributes)
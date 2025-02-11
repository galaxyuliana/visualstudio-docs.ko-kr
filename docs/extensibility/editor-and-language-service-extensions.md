---
title: 편집기 및 언어 서비스 확장 | Microsoft Docs
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- editors [Visual Studio SDK]
ms.assetid: 5653bac9-724f-4948-a820-68ce6aa96365
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 1df6f65db70425650fc2860bf5ddf6e2d2e203c6
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66353379"
---
# <a name="editor-and-language-service-extensions"></a>편집기 및 언어 서비스 확장
Visual Studio 코드 편집기의 대부분의 기능을 확장할 수 있습니다. 편집기는 Windows Presentation Foundation (WPF)에 기반 하 고 관리 코드에 기록 됩니다. 이전 버전의 Visual Studio의 디자인에서이 디자인 다른 하지만 같은 기능을 대부분을 제공 합니다. 편집기를 확장 하는 프레임 워크 MEF (Managed Extensibility)를 사용 합니다.

 Visual Studio SDK 라고도 하는 어댑터를 제공 *shim* 이전 버전용으로 작성 된 Vspackage를 지원 하도록 합니다. 그럼에도 불구 하 고는 기존 VSPackage가 더 나은 성능 및 안정성을 가져올 새 기술 업데이트 하는 것이 좋습니다.

## <a name="related-topics"></a>관련 항목

|제목|설명|
|-----------|-----------------|
|[편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)|편집기 항목 템플릿을 사용 하 여 소개 합니다.|
|[편집기 및 언어 서비스 확장](../extensibility/extending-the-editor-and-language-services.md)|디자인 및 핵심 편집기의 기능을 소개 하 고 확장 하는 방법을 보여 주는 문서에 연결 합니다.|
|[편집기에서 레거시 인터페이스](../extensibility/legacy-interfaces-in-the-editor.md)|기존 코드에서 핵심 편집기에 액세스 하는 방법에 설명 하는 문서에 연결 합니다.|
|[사용자 지정 편집기 및 디자이너 만들기](../extensibility/creating-custom-editors-and-designers.md)|사용자 지정 편집기를 만드는 방법에 설명 하는 문서에 연결 합니다.|
|[레거시 언어 서비스 확장성](../extensibility/internals/legacy-language-service-extensibility.md)|Visual Studio 프로그래밍 언어를 통합 하는 방법에 설명 하는 문서에 연결 합니다.|
|[MEF(Managed Extensibility Framework)](/dotnet/framework/mef/index)|Managed Extensibility Framework (MEF)를 소개합니다.|
|[Windows Presentation Foundation](/dotnet/framework/wpf/index)|Windows Presentation Foundation (WPF)를 소개합니다.|
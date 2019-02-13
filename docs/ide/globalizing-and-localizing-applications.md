---
title: 애플리케이션 전역화 및 지역화
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- globalization [Visual Studio]
- Visual Basic code, international applications
- C#, international applications
- localization [Visual Studio]
- world-ready applications
- international applications [Visual Studio]
ms.assetid: 4d9815ae-3e80-4b4d-933d-f8309aee18d5
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: b3b8628f61c5fa2bc6eebadad23d5c9133f6fe4c
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55907350"
---
# <a name="globalizing-and-localizing-applications"></a>애플리케이션 전역화 및 지역화

애플리케이션을 전 세계의 대상에게 배포할 계획이라면 설계 및 개발 단계에서 몇 가지 사항을 고려해야 합니다. 이런 계획이 없더라도 애플리케이션의 미래 버전에서 계획이 변경될 경우 미리 작은 노력으로 작업을 훨씬 더 간소화할 수 있습니다. [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에 기본 제공된 서비스를 사용하면 Visual Studio에서 관리 개발을 통해 다양한 로캘에 맞게 조정될 수 있는 단일 애플리케이션을 쉽게 개발할 수 있습니다.

## <a name="resources"></a>자료

 Visual Studio는 처음부터 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에 기본 제공된 서비스를 이용하여 전 세계의 대상을 위해 쉽게 개발할 수 있도록 고안되었습니다. 다음 문서에서는 Visual Studio에 기본 제공된 국제화 기능을 소개합니다.

 [.NET Framework 기반의 국가별 애플리케이션 소개](../ide/introduction-to-international-applications-based-on-the-dotnet-framework.md) Visual Studio 및 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]을 사용하여 국제 시장용 소프트웨어를 개발하는 방법에 대한 개념을 소개합니다.

 [애플리케이션 지역화](../ide/localizing-applications.md) 특정 문화권에 맞게 애플리케이션을 사용자 지정하는 방법에 대한 페이지의 링크를 제공합니다.

 [애플리케이션 전역화](../ide/globalizing-applications.md) 여러 문화권을 지원하는 애플리케이션을 만드는 방법에 대한 페이지의 링크를 제공합니다.

## <a name="see-also"></a>참고 항목

- [지역화 대비 애플리케이션 개발을 위한 최선의 구현 방법](/dotnet/standard/globalization-localization/best-practices-for-developing-world-ready-apps)에서는 전 세계 대상을 위한 프로그래밍에 대한 배경 정보를 제공합니다.
- [클래스 라이브러리 개요](/dotnet/standard/class-library-overview)에서는 개발 과정을 단축하고 최적화하며 시스템 기능에 액세스할 수 있는 클래스, 인터페이스, 값 형식을 소개합니다.
- <xref:System.Globalization>은 언어, 국가/지역, 사용하는 달력, 날짜, 통화 및 숫자 형식 패턴, 문자열 정렬 순서 등의 문화권 관련 정보를 정의하는 이 네임스페이스의 클래스를 나타냅니다.
- <xref:System.Resources>는 애플리케이션에 사용되는 여러 가지 문화권별 리소스를 개발자가 만들고, 저장하고, 관리할 수 있게 하는 이 네임스페이스의 클래스와 인터페이스를 나타냅니다.
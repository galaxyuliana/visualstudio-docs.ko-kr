---
title: N 계층 데이터 애플리케이션 개요
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- presentation tier
- middle tier
- data tier
- n-tier applications, about n-tier applications
ms.assetid: 1020581d-eaaa-41a2-aca4-bf4c212895f6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: e4c10e3a337b44a4b7c9a1cb59165736bb3e7efb
ms.sourcegitcommit: 2da366ba9ad124366f6502927ecc720985fc2f9e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/09/2019
ms.locfileid: "68871523"
---
# <a name="n-tier-data-applications-overview"></a>N 계층 데이터 애플리케이션 개요
*N 계층* 데이터 응용 프로그램은 여러 *계층*으로 구분 되는 데이터 응용 프로그램입니다. "분산 응용 프로그램" 및 "다중 계층 응용 프로그램" 이라는 n 계층 응용 프로그램은 클라이언트와 서버 간에 분산 된 불연속 계층으로 처리를 분리 합니다. 데이터에 액세스 하는 응용 프로그램을 개발 하는 경우 응용 프로그램을 구성 하는 다양 한 계층을 명확 하 게 구분 해야 합니다.

일반적인 N 계층 애플리케이션에는 프레젠테이션 계층, 중간 계층 및 데이터 계층이 포함됩니다. N 계층 응용 프로그램에서 다양 한 계층을 분리 하는 가장 쉬운 방법은 응용 프로그램에 포함 하려는 각 계층에 대 한 불연속 프로젝트를 만드는 것입니다. 예를 들어 프레젠테이션 계층은 Windows Forms 응용 프로그램 일 수 있지만 데이터 액세스 논리는 중간 계층에 위치한 클래스 라이브러리 일 수 있습니다. 또한 프레젠테이션 계층은 웹 서비스와 같은 서비스를 통해 중간 계층의 데이터 액세스 논리와 통신할 수 있습니다. 애플리케이션 구성 요소를 별도의 계층으로 분리하면 애플리케이션의 유지 관리성과 확장성이 높아집니다. 이렇게 하려면 전체 솔루션을 다시 디자인 해야 할 필요 없이 단일 계층에 적용할 수 있는 새로운 기술을 더 쉽게 채택할 수 있습니다. 또한 n 계층 응용 프로그램은 일반적으로 프레젠테이션 계층에서 격리를 유지 하는 중간 계층에 중요 한 정보를 저장 합니다.

Visual Studio에는 개발자가 n 계층 응용 프로그램을 만드는 데 도움이 되는 몇 가지 기능이 포함 되어 있습니다.

- 데이터 집합은 데이터 집합 (데이터 엔터티 계층) 및 Tableadapter (데이터 액세스 계층)를 불연속 프로젝트로 분리할 수 있도록 하는 **데이터 집합 프로젝트** 속성을 제공 합니다.

- [Visual Studio의 LINQ to SQL 도구](../data-tools/linq-to-sql-tools-in-visual-studio2.md) 는 DataContext 및 데이터 클래스를 별도의 네임 스페이스로 생성 하는 설정을 제공 합니다. 이렇게 하면 데이터 액세스 및 데이터 엔터티 계층을 논리적으로 분리할 수 있습니다.

- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 는 응용 <xref:System.Data.Linq.Table%601.Attach%2A> 프로그램의 여러 계층 으로부터 DataContext를 가져오는 데 사용할 수 있는 메서드를 제공 합니다. 자세한 내용은 [LINQ to SQL를 사용 하는 N 계층 및 원격 응용 프로그램](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)을 참조 하세요.

## <a name="presentation-tier"></a>프레젠테이션 계층
*프레젠테이션 계층* 은 사용자가 응용 프로그램과 상호 작용 하는 계층입니다. 추가 응용 프로그램 논리도 포함 하는 경우가 많습니다. 일반적인 프레젠테이션 계층 구성 요소에는 다음이 포함 됩니다.

- 데이터 바인딩 구성 요소 (예: <xref:System.Windows.Forms.BindingSource> 및 <xref:System.Windows.Forms.BindingNavigator>)

- 프레젠테이션 계층에서 사용할 엔터티 클래스 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 같은 데이터의 개체 표현입니다.

프레젠테이션 계층은 일반적으로 서비스 참조 (예: [Visual Studio 응용 프로그램의 Windows Communication Foundation 서비스 및 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md) )를 사용 하 여 중간 계층에 액세스 합니다. 프레젠테이션 계층은 데이터 계층에 직접 액세스 하지 않습니다. 프레젠테이션 계층은 중간 계층의 데이터 액세스 구성 요소를 기준으로 데이터 계층과 통신 합니다.

## <a name="middle-tier"></a>중간 계층
*중간 계층* 은 프레젠테이션 계층과 데이터 계층에서 서로 통신 하는 데 사용 하는 계층입니다. 일반적인 중간 계층 구성 요소에는 다음이 포함 됩니다.

- 비즈니스 규칙 및 데이터 유효성 검사 등의 비즈니스 논리

- 데이터 액세스 구성 요소 및 논리 (예:

  - [Tableadapter](create-and-configure-tableadapters.md) 및 [Dataadapter 및 datareaders](/dotnet/framework/data/adonet/dataadapters-and-datareaders).

  - [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 엔터티 클래스와 같은 데이터의 개체 표현입니다.

  - 인증, 권한 부여, 개인 설정 등의 일반적인 응용 프로그램 서비스입니다.

다음 그림에서는 Visual Studio에서 사용할 수 있는 기능 및 기술과 n 계층 응용 프로그램의 중간 계층에 적합할 수 있는 기술을 보여 줍니다.

![중간 계층 구성](../data-tools/media/ntiermid.png) 요소 중간 계층

중간 계층은 일반적으로 데이터 연결을 사용 하 여 데이터 계층에 연결 합니다. 이 데이터 연결은 일반적으로 데이터 액세스 구성 요소에 저장 됩니다.

## <a name="data-tier"></a>데이터 계층
*데이터 계층* 은 기본적으로 응용 프로그램의 데이터를 저장 하는 서버 (예: SQL Server을 실행 하는 서버)입니다.

다음 그림에서는 Visual Studio에서 사용할 수 있는 기능 및 기술과 n 계층 응용 프로그램의 데이터 계층에 적합할 수 있는 기술을 보여 줍니다.

![데이터 계층 구성](../data-tools/media/ntierdatatier.png) 요소 데이터 계층

프레젠테이션 계층의 클라이언트에서 직접 데이터 계층에 액세스할 수 없습니다. 대신, 중간 계층의 데이터 액세스 구성 요소는 프레젠테이션과 데이터 계층 간의 통신에 사용 됩니다.

## <a name="help-for-n-tier-development"></a>N 계층 개발에 대 한 도움말
다음 항목에서는 n 계층 응용 프로그램 작업에 대 한 정보를 제공 합니다.

[데이터 집합 및 TableAdapter를 다른 프로젝트로 분리](../data-tools/separate-datasets-and-tableadapters-into-different-projects.md)

[연습: N 계층 데이터 애플리케이션 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)

[LINQ to SQL을 사용한 N 계층 및 원격 애플리케이션](/dotnet/framework/data/adonet/sql/linq/n-tier-and-remote-applications-with-linq-to-sql)

## <a name="see-also"></a>참고자료

- [연습: N 계층 데이터 애플리케이션 만들기](../data-tools/walkthrough-creating-an-n-tier-data-application.md)
- [계층적 업데이트](../data-tools/hierarchical-update.md)
- [Visual Studio의 데이터 집합 도구](../data-tools/dataset-tools-in-visual-studio.md)
- [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)

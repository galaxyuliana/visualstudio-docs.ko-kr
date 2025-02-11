---
title: 다른 버전의 Microsoft Office에서 솔루션을 실행 합니다.
ms.date: 02/02/2017
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- solutions [Office development in Visual Studio], multiple Office versions
- Office applications [Office development in Visual Studio], multiple Office versions
- Office development in Visual Studio, multiple Office versions
- Office solutions [Office development in Visual Studio]
- multiple Office versions
author: John-Hart
ms.author: johnhart
manager: jillfra
ms.workload:
- office
ms.openlocfilehash: 4db3b9694ed8a21786933c3975e9f0970f60c7aa
ms.sourcegitcommit: 94b3a052fb1229c7e7f8804b09c1d403385c7630
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "62978421"
---
# <a name="run-solutions-in-different-versions-of-microsoft-office"></a>다른 버전의 Microsoft Office에서 솔루션을 실행 합니다.

## <a name="run-office-solutions-created-by-using-visual-studio-2010-and-above"></a>Visual Studio 2010을 사용 하 고 위에서 만든 Office 솔루션 실행

|프로젝트 템플릿이 대상으로 하는 Office 버전|프로젝트의 대상.NET Framework<sup>1</sup>|솔루션을 실행할 수 있는 Office 버전|최종 사용자 컴퓨터에 필요한 런타임|
|--------------------------------------------------------|------------------------------------------------------|--------------------------------------------------|-------------------------------------------|
|Office 2016 및 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 Microsoft Office system<sup>2</sup>|Visual Studio 2010 Tools for Office Runtime|
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 Microsoft Office system<sup>2</sup>|Visual Studio 2010 Tools for Office Runtime|
|[!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|.NET Framework 3.5|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]|Visual Studio 2010 Tools for Office Runtime|
|2007 Microsoft Office System|[!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 이상<br /><br /> 또는<br /><br /> .NET Framework 3.5|Office 2016<br /><br /> [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)]<br /><br /> [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]<br /><br /> 2007 Microsoft Office System|Visual Studio 2010 Tools for Office Runtime|

 1. .NET Framework 버전이 프로젝트의 대상이 솔루션을 실행 하려면 최종 사용자 컴퓨터에 필요한 것입니다. 예를 들어, 프로젝트가.NET Framework 3.5를 대상으로 하는 경우.NET Framework 3.5 최종 사용자 컴퓨터에 필요 합니다. 이 예제에서는 솔루션이 실행 되지 것입니다 경우는 [!INCLUDE[net_v40_short](../sharepoint/includes/net-v40-short-md.md)] 최종 사용자 컴퓨터에 설치 됩니다.

 2. 이 시나리오에서는 솔루션이 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]의 새로운 기능을 사용하지 않는 경우에만 2007 Microsoft Office system에서 오류 없이 실행됩니다.

## <a name="run-office-solutions-created-by-using-versions-of-visual-studio-prior-to-visual-studio-2010"></a>버전의 Visual Studio 2010 이전의 Visual Studio를 사용 하 여 만든 Office 솔루션 실행
 Microsoft Office 애플리케이션은 Visual Studio 2010 이전의 Visual Studio 버전을 사용하여 만든 솔루션을 실행할 수 있습니다. 경우에 따라 이러한 솔루션에는 서로 다른 버전의 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]이 필요합니다. 서로 다른 버전의는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 동일한 컴퓨터에 나란히 설치할 수 있습니다.

 다음 표에서 버전의 Microsoft Office 이전 버전의 Visual Studio를 사용 하 여 만든 솔루션을 실행할 수 있습니다 및 버전을 보여 줍니다는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] .NET Framework는 각 솔루션에 대 한 필수입니다.

|솔루션을 만드는 데 사용되는 Visual Studio 버전|프로젝트 템플릿이 대상으로 하는 Office 버전|솔루션을 실행할 수 있는 Office 버전|최종 사용자 컴퓨터에 필요한 런타임|최종 사용자 컴퓨터에 필요한.NET Framework 버전|
|----------------------------------------------------------|--------------------------------------------------------|--------------------------------------------------|-------------------------------------------|----------------------------------------------------------|
|Visual Studio 2008 Professional<br /><br /> 또는<br /><br /> Visual Studio Team System 2008|2007 Microsoft Office System|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] <sup>1</sup><br /><br /> 2007 Microsoft Office System|Visual Studio 2010 Tools for Office Runtime<sup>1</sup><br /><br /> 또는<br /><br /> Visual Studio Tools for the Microsoft Office system(버전 3.0 런타임)|.NET Framework 3.5|
|VSTO 2005 SE를 사용 하 여 Visual Studio 2005의 다음 버전 중 하나<sup>2</sup> 설치:<br /><br /> -Visual Studio 2005 Tools for Office<br />-   Visual Studio Team System 2005<br />-   Visual Studio 2005 Professional|2007 Microsoft Office System|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] (32 비트 전용<sup>3</sup>)<br /><br /> 2007 Microsoft Office System|Visual Studio 2005 Tools for Office Second Edition Runtime|.NET Framework 2.0, .NET Framework 3.0 또는 .NET Framework 3.5|
|다음 Visual Studio 버전 중 하나:<br /><br /> -   Visual Studio 2008 Professional<br />-   Visual Studio Team System 2008<br />-Visual Studio 2005 Tools for Office (VSTO 2005 SE 유무<sup>2</sup> 설치)<br />-Visual Studio Team System 2005 (VSTO 2005 SE 유무<sup>2</sup> 설치)<br />-VSTO 2005 SE를 사용 하 여 visual Studio 2005 Professional<sup>2</sup> 설치|Microsoft Office 2003|[!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] (32 비트 전용<sup>3</sup>)<br /><br /> 2007 Microsoft Office System<br /><br /> Microsoft Office 2003|Visual Studio 2005 Tools for Office Second Edition Runtime|.NET Framework 2.0, .NET Framework 3.0 또는 .NET Framework 3.5|

 1. [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)] 응용 프로그램에는 Visual Studio 2010 Tools for Office 런타임 포함 합니다. 따라서 이러한 응용 프로그램 항상 사용 하 여 Visual Studio Tools를 사용 하지 않고 Visual Studio 2010 Tools for Office 런타임에서 Microsoft Office system (버전 3.0 런타임)이이 시나리오에서는 합니다. 2007 Microsoft Office system의 애플리케이션은 Visual Studio 2010 Tools for Office Runtime 또는 Visual Studio Tools for the Microsoft Office system(버전 3.0 런타임)을 사용할 수 있습니다.

 2. VSTO 2005 SE는 Microsoft Office 2003 및 2007 Microsoft Office system용 VSTO 추가 기능 프로젝트 템플릿을 제공하는 무료 Visual Studio 추가 기능입니다. VSTO 2005 SE는 Visual Studio 2005 Professional, Visual Studio 2005 Tools for Office 또는 Visual Studio Team System 2005의 버전과 함께 설치될 수 있습니다. 자세한 내용은 [Visual Studio 2005 Tools for Office Second Edition](http://go.microsoft.com/fwlink/?LinkId=148446)합니다.

 3. Visual Studio 2005 Tools for Office Second Edition Runtime이 필요한 Office 솔루션은 64비트 버전의 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 및 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]과 호환되지 않습니다. 64비트 버전의 [!INCLUDE[Office_15_short](../vsto/includes/office-15-short-md.md)] 또는 [!INCLUDE[office14_long](../vsto/includes/office14-long-md.md)]에서 이러한 솔루션을 실행하려면 2007 Microsoft Office system을 대상으로 하는 [!INCLUDE[vs_dev10_long](../sharepoint/includes/vs-dev10-long-md.md)] 또는 Visual Studio 2008 프로젝트로 프로젝트를 업그레이드해야 합니다.

## <a name="see-also"></a>참고자료
- [Office 솔루션을 만들고 디자인](../vsto/designing-and-creating-office-solutions.md)
- [Visual Studio Tools for Office 런타임 개요](../vsto/visual-studio-tools-for-office-runtime-overview.md)
- [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)
- [Visual Studio Tools for Office 런타임 설치 시나리오](../vsto/visual-studio-tools-for-office-runtime-installation-scenarios.md)
- [Office 솔루션을 개발 하도록 컴퓨터를 구성 합니다.](../vsto/running-solutions-in-different-versions-of-microsoft-office.md)

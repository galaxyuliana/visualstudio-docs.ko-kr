---
title: '연습: Windows Forms에서 간단한 WCF 서비스 만들기'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- WCF, walkthrough [Visual Studio]
- WCF, Visual Studio tools for
- WCF services
- WCF services, walkthrough
ms.assetid: 5fef1a64-27a4-4f10-aa57-29023e28a2d6
author: gewarren
ms.author: gewarren
manager: jillfra
ms.workload:
- data-storage
ms.openlocfilehash: 08b55652fbadd0b27f4519b94e083409c9de3af5
ms.sourcegitcommit: 21d667104199c2493accec20c2388cf674b195c3
ms.translationtype: MTE95
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2019
ms.locfileid: "55951113"
---
# <a name="walkthrough-create-a-simple-wcf-service-in-windows-forms"></a>연습: Windows Forms에서 간단한 WCF 서비스 만들기

이 연습에서는 간단한 [!INCLUDE[vsindigo](../data-tools/includes/vsindigo_md.md)] 서비스를 만들고 테스트한 다음 Windows Forms 응용 프로그램에서 액세스하는 방법을 보여 줍니다.

[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]

## <a name="create-the-service"></a>서비스 만들기

### <a name="to-create-a-wcf-service"></a>WCF 서비스를 만들려면

1.  **파일** 메뉴에서 **새로 만들기** 를 가리킨 다음 **프로젝트**를 클릭합니다.

2.  **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **Visual C#** 노드를 확장한 다음, **WCF**, **WCF 서비스 라이브러리**를 차례로 클릭합니다. **확인**을 클릭하여 프로젝트를 엽니다.

     ![WCF 서비스 라이브러리 프로젝트](../data-tools/media/wcf1.png)

    > [!NOTE]
    >  이렇게 하면 테스트 및 액세스할 수 있는 작업 서비스가 만들어집니다. 다음 두 단계는 다른 데이터 형식을 사용하도록 기본 메서드를 수정하는 방법을 보여 줍니다. 실제 응용 프로그램에서는 서비스에 사용자 고유의 함수를 추가할 수도 있습니다.

3.  ![IService1 파일](../data-tools/media/wcf2.png)

     **솔루션 탐색기**에서 **IService1.vb** 또는 **IService1.cs**를 두 번 클릭하고 다음 줄을 찾습니다.

     [!code-csharp[WCFWalkthrough#4](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.cs)]
     [!code-vb[WCFWalkthrough#4](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_1.vb)]

     형식을 변경 합니다 `value` 문자열 매개 변수:

     [!code-csharp[WCFWalkthrough#1](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.cs)]
     [!code-vb[WCFWalkthrough#1](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_2.vb)]

     위의 코드에서 `<OperationContract()>` 또는 `[OperationContract]` 특성을 확인합니다. 이러한 특성은 서비스에서 노출하는 모든 메서드에 필요합니다.

4.  ![Service1 파일](../data-tools/media/wcf3.png)

     **솔루션 탐색기**에서 **Service1.vb** 또는 **Service1.cs**를 두 번 클릭하고 다음 줄을 찾습니다.

     [!code-vb[WCFWalkthrough#5](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.vb)]
     [!code-csharp[WCFWalkthrough#5](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_3.cs)]

     형식을 변경 합니다 `value` 문자열 매개 변수:

     [!code-csharp[WCFWalkthrough#2](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.cs)]
     [!code-vb[WCFWalkthrough#2](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_4.vb)]

## <a name="test-the-service"></a>서비스 테스트

### <a name="to-test-a-wcf-service"></a>WCF 서비스를 테스트하려면

1.  **F5** 키를 눌러 서비스를 실행합니다. A **WCF 테스트 클라이언트** 폼 표시 되 고 서비스를 로드 합니다.

2.  **WCF 테스트 클라이언트** 폼에서 **IService1** 아래의 **GetData()** 메서드를 두 번 클릭합니다. 합니다 **GetData** 탭이 표시 됩니다.

     ![GetData&#40; &#41; 메서드](../data-tools/media/wcf4.png)

3.  **요청** 상자에서 **값** 필드와 형식 `Hello`를 선택합니다.

     ![값 필드](../data-tools/media/wcf5.png)

4.  **호출** 단추를 클릭합니다. 경우는 **보안 경고** 대화 상자가 나타나면 **확인**합니다. 결과에 표시 된 **응답** 상자입니다.

     ![응답 상자의 결과](../data-tools/media/wcf6.png)

5.  **파일** 메뉴에서 **끝내기**를 클릭하여 테스트 폼을 닫습니다.

## <a name="access-the-service"></a>서비스에 액세스

### <a name="to-reference-a-wcf-service"></a>WCF 서비스를 참조하려면

1.  **파일** 메뉴에서 **추가**를 가리킨 다음, **새 프로젝트**를 클릭합니다.

2.  에 **새 프로젝트** 대화 상자에서 **Visual Basic** 또는 **시각적 C#**  노드를 선택 **Windows**를 선택한 다음  **Windows Forms 응용 프로그램**합니다. **확인**을 클릭하여 프로젝트를 엽니다.

     ![Windows Forms 응용 프로그램 프로젝트](../data-tools/media/wcf7.png)

3.  **WindowsApplication1**을 마우스 오른쪽 단추로 클릭하고 **서비스 참조 추가**를 클릭합니다. 합니다 **서비스 참조 추가** 대화 상자가 나타납니다.

4.  **서비스 참조 추가** 대화 상자에서 **검색**을 클릭합니다.

     ![서비스 참조 추가 대화 상자](../data-tools/media/wcf8.png)

     **Service1** 에 표시 합니다 **Services** 창입니다.

5.  **확인**을 클릭하여 서비스 참조를 추가합니다.

### <a name="to-build-a-client-application"></a>클라이언트 응용 프로그램을 빌드하려면

1.  Windows Forms 디자이너를 아직 열지 않은 경우 **솔루션 탐색기**에서 **Form1.vb** 또는 **Form1.cs**을 두 번 클릭하여 엽니다.

2.  **도구 상자**에서 `TextBox` 컨트롤, `Label` 컨트롤 및 `Button` 컨트롤을 폼으로 끌어옵니다.

     ![폼에 컨트롤 추가](../data-tools/media/wcf9.png)

3.  `Button`을 두 번 클릭하고 다음 코드를 `Click` 이벤트 처리기에 추가합니다.

     [!code-csharp[WCFWalkthrough#3](../data-tools/codesnippet/CSharp/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.cs)]
     [!code-vb[WCFWalkthrough#3](../data-tools/codesnippet/VisualBasic/walkthrough-creating-a-simple-wcf-service-in-windows-forms_5.vb)]

4.  **솔루션 탐색기**에서 **WindowsApplication1**을 마우스 오른쪽 단추로 클릭한 다음, **시작 프로젝트로 설정**을 클릭합니다.

5.  **F5** 키를 눌러 프로젝트를 실행합니다. 텍스트를 입력하고 단추를 클릭합니다. 레이블 표시 "입력:" 입력 텍스트를 표시 합니다.

     ![결과가 표시된 폼](../data-tools/media/wcf10.png)

## <a name="see-also"></a>참고 항목

- [Windows Communication Foundation 서비스 및 Visual Studio의 WCF Data Services](../data-tools/windows-communication-foundation-services-and-wcf-data-services-in-visual-studio.md)
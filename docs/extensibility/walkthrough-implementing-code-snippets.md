---
title: '연습: 코드 조각 구현 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: adbc5382-d170-441c-9fd0-80faa1816478
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 2e4b6d0346ce10c780254b26a4f2c710ed171ef5
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66320730"
---
# <a name="walkthrough-implement-code-snippets"></a>연습: 코드 조각 구현
코드 조각을 작성 하 고 확장의 사용자가 자신의 코드에 추가할 수 있도록 편집기 확장에 포함할 수 있습니다.

 코드 조각에는 코드 또는 파일에 통합할 수 있는 기타 텍스트의 일부입니다. 특정 프로그래밍 언어에 대 한 등록 된 모든 조각을 보려면 합니다 **도구** 메뉴에서 클릭 **코드 조각 관리자**합니다. 코드 조각에서 원하는 위치를 마우스 오른쪽 단추로 파일에서 조각을 삽입 하려면 다음 코드 조각 삽입 또는 **감싸기**원하는 코드 조각을 찾아서 두 번 클릭 합니다. 키를 눌러 **탭** 하거나 **Shift**+**탭** 조각의 관련 부분을 수정 하 여 키를 누릅니다 **Enter** 또는 **Esc** 계약에 동의 합니다. 자세한 내용은 [코드 조각](../ide/code-snippets.md)합니다.

 코드 조각.snippet * 파일 이름 확장명을 가진 XML 파일에 포함 됩니다. 코드 조각을 사용자 찾아 변경할 수 있도록 코드 조각 삽입 된 후 강조 표시 되는 필드를 포함할 수 있습니다. 코드 조각 파일에 대 한 정보도 제공 합니다 **코드 조각 관리자** 올바른 범주에서 조각 이름을 표시할 수 있도록 합니다. 코드 조각 스키마에 대 한 자세한 내용은 [코드 조각 스키마 참조](../ide/code-snippets-schema-reference.md)합니다.

 이 연습에서는 이러한 작업을 수행 하는 방법에 설명 합니다.

1. 만들어 특정 언어에 대 한 코드 조각 등록 합니다.

2. 추가 된 **코드 조각 삽입** 바로 가기 메뉴에 명령 합니다.

3. 코드 조각 확장을 구현 합니다.

   이 연습은 기반으로 [연습: 문 완성 표시](../extensibility/walkthrough-displaying-statement-completion.md)합니다.

## <a name="prerequisites"></a>전제 조건
 Visual Studio 2015부터 있습니다 다운로드 센터에서 Visual Studio SDK를 설치 하지 마세요. Visual Studio 설치에서 선택적 기능으로 포함 되어 있습니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.

## <a name="create-and-register-code-snippets"></a>만들기 및 코드 조각 등록
 일반적으로 코드 조각은 등록 된 언어 서비스를 사용 하 여 연결 합니다. 그러나 구현할 필요가 없습니다를 <xref:Microsoft.VisualStudio.Package.LanguageService> 코드 조각 등록 합니다. 대신 조각 인덱스 파일의 GUID를 지정 하 고 다음에서 동일한 GUID를 사용 하 여는 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> 프로젝트에 추가 하는 합니다.

 다음 단계에는 코드 조각을 만드는 특정 GUID를 사용 하 여 연결 하는 방법을 보여 줍니다.

1. 다음 디렉터리 구조를 만듭니다.

    **%InstallDir%\TestSnippets\Snippets\1033\\**

    여기서 *% InstallDir %* Visual Studio 설치 폴더입니다. (하지만이 경로 일반적으로 코드 조각을 설치할 데를 지정할 수 있습니다 모든 경로.)

2. \1033\ 폴더를 만듭니다는 *.xml* 파일을 이름을 **TestSnippets.xml**합니다. (이 이름이 조각 인덱스 파일에 대 한 일반적으로 사용 되지만 붙어 있다면 이름을 지정할 수 있습니다는 *.xml* 파일 이름 확장명.) 다음 텍스트를 추가 합니다. 다음 자리 표시자 GUID는 삭제 하 고 직접 추가 합니다.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <SnippetCollection>
       <Language Lang="TestSnippets" Guid="{00000000-0000-0000-0000-000000000000}">
           <SnippetDir>
               <OnOff>On</OnOff>
               <Installed>true</Installed>
               <Locale>1033</Locale>
               <DirPath>%InstallRoot%\TestSnippets\Snippets\%LCID%\</DirPath>
               <LocalizedName>Snippets</LocalizedName>
           </SnippetDir>
       </Language>
   </SnippetCollection>
   ```

3. 코드 조각 폴더에 파일을 만듭니다, 이름을 **테스트**`.snippet`, 후 다음 텍스트를 추가 합니다.

   ```xml
   <?xml version="1.0" encoding="utf-8" ?>
   <CodeSnippets  xmlns="http://schemas.microsoft.com/VisualStudio/2005/CodeSnippet">
       <CodeSnippet Format="1.0.0">
           <Header>
               <Title>Test replacement fields</Title>
               <Shortcut>test</Shortcut>
               <Description>Code snippet for testing replacement fields</Description>
               <Author>MSIT</Author>
               <SnippetTypes>
                   <SnippetType>Expansion</SnippetType>
               </SnippetTypes>
           </Header>
           <Snippet>
               <Declarations>
                   <Literal>
                     <ID>param1</ID>
                       <ToolTip>First field</ToolTip>
                       <Default>first</Default>
                   </Literal>
                   <Literal>
                       <ID>param2</ID>
                       <ToolTip>Second field</ToolTip>
                       <Default>second</Default>
                   </Literal>
               </Declarations>
               <References>
                  <Reference>
                      <Assembly>System.Windows.Forms.dll</Assembly>
                  </Reference>
               </References>
               <Code Language="TestSnippets">
                   <![CDATA[MessageBox.Show("$param1$");
        MessageBox.Show("$param2$");]]>
               </Code>
           </Snippet>
       </CodeSnippet>
   </CodeSnippets>
   ```

   다음 단계에는 코드 조각은 등록 하는 방법을 보여 줍니다.

### <a name="to-register-code-snippets-for-a-specific-guid"></a>특정 GUID에 대 한 코드 조각 등록

1. 엽니다는 **CompletionTest** 프로젝트입니다. 이 프로젝트를 만드는 방법에 대 한 자세한 내용은 [연습: 문 완성 표시](../extensibility/walkthrough-displaying-statement-completion.md)합니다.

2. 프로젝트에서 다음 어셈블리에 대 한 참조를 추가 합니다.

    - Microsoft.VisualStudio.TextManager.Interop

    - Microsoft.VisualStudio.TextManager.Interop.8.0

    - microsoft.msxml

3. 프로젝트에서 엽니다는 **source.extension.vsixmanifest** 파일입니다.

4. 있는지 확인 합니다 **자산** 탭에는 **VsPackage** 형식의 콘텐츠 **프로젝트** 프로젝트의 이름으로 설정 됩니다.

5. CompletionTest 프로젝트를 선택 하 고 속성 창에서 설정 **Pkgdef 파일 생성** 하 **true**합니다. 프로젝트를 저장합니다.

6. 추가 정적 `SnippetUtilities` 프로젝트에 클래스입니다.

     [!code-csharp[VSSDKCompletionTest#22](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_1.cs)]
     [!code-vb[VSSDKCompletionTest#22](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_1.vb)]

7. SnippetUtilities 클래스 GUID를 정의 하 고에서 사용한 값을 제공 합니다 *SnippetsIndex.xml* 파일입니다.

     [!code-csharp[VSSDKCompletionTest#23](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_2.cs)]
     [!code-vb[VSSDKCompletionTest#23](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_2.vb)]

8. 추가 된 <xref:Microsoft.VisualStudio.Shell.ProvideLanguageCodeExpansionAttribute> 에 `TestCompletionHandler` 클래스입니다. 이 특성은 프로젝트의 모든 public 또는 internal (비정적) 클래스에 추가할 수 있습니다. (추가 해야 할 수는 `using` Microsoft.VisualStudio.Shell 네임 스페이스에 대 한 문입니다.)

     [!code-csharp[VSSDKCompletionTest#24](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_3.cs)]
     [!code-vb[VSSDKCompletionTest#24](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_3.vb)]

9. 프로젝트를 빌드하고 실행합니다. 프로젝트를 실행할 때 시작 되는 Visual Studio의 실험적 인스턴스에서 방금 등록 코드 조각에 표시 해야 합니다 **코드 조각 관리자** 아래 합니다 **TestSnippets** 언어입니다.

## <a name="add-the-insert-snippet-command-to-the-shortcut-menu"></a>코드 조각 삽입 명령을 바로 가기 메뉴에 추가
 합니다 **코드 조각 삽입** 명령 텍스트 파일에 대 한 바로 가기 메뉴에 포함 되지 않습니다. 따라서 명령을 활성화 해야 합니다.

#### <a name="to-add-the-insert-snippet-command-to-the-shortcut-menu"></a>바로 가기 메뉴에 코드 조각 삽입 명령을 추가 하려면

1. 열기는 `TestCompletionCommandHandler` 클래스 파일입니다.

     이 클래스를 구현 하므로 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>을 활성화할 수 있습니다 합니다 **조각 삽입** 명령을 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드. 명령을 사용 하기 전에이 메서드는 호출 되지 않는 automation 함수 내에서 때문에 확인 때 합니다 **코드 조각 삽입** 명령을 클릭할 코드 조각 선택 사용자 인터페이스 (UI)를 표시 합니다.

     [!code-csharp[VSSDKCompletionTest#25](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_4.cs)]
     [!code-vb[VSSDKCompletionTest#25](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_4.vb)]

2. 프로젝트를 빌드하고 실행합니다. 실험적 인스턴스에서 포함 된 파일을 엽니다는 *.zzz* 파일 이름 확장명을 마우스 오른쪽 단추로 클릭 어디에 있습니다. 합니다 **코드 조각 삽입** 명령이 바로 가기 메뉴에 표시 해야 합니다.

## <a name="implement-snippet-expansion-in-the-snippet-picker-ui"></a>코드 조각 선택 UI에서 코드 조각 확장을 구현 합니다.
 이 섹션에서는 코드 조각 선택기 UI 되도록 코드 조각 확장을 구현 하는 방법을 선택할 때 표시 된 **코드 조각 삽입** 바로 가기 메뉴를 클릭 한 합니다. 사용자 형식 코드 조각 바로 가기 키를 누를 때 코드 조각도 확장 됩니다 **탭**합니다.

 코드 조각 선택기 UI를 표시 하 고 탐색 및 승인 후 삽입 조각 수 있도록 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드. 삽입 자체에서 처리 되는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> 메서드.

 코드 조각 확장의 구현을 사용 하 여 레거시 <xref:Microsoft.VisualStudio.TextManager.Interop> 인터페이스입니다. 현재 편집기 클래스에서 레거시 코드를 변환 하는 경우에 레거시 인터페이스가 조합을 줄 번호 및 열 번호를 사용 하 여 텍스트 버퍼에 위치를 지정 하는 현재 클래스는 하나의 인덱스를 사용 해야 합니다. 따라서 버퍼에 세 줄을 각각에 10 개의 문자 (+ 한 문자로 계산 하는 줄 바꿈,), 세 번째 줄에서 네 번째 문자는 현재 구현에서 27 위치는 아니지만 2 번 줄에서 기존 구현에는 3을 배치 합니다.

#### <a name="to-implement-snippet-expansion"></a>코드 조각 확장을 구현 하려면

1. 포함 된 파일에는 `TestCompletionCommandHandler` 클래스에 다음 코드를 추가 `using` 문입니다.

     [!code-csharp[VSSDKCompletionTest#26](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_5.cs)]
     [!code-vb[VSSDKCompletionTest#26](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_5.vb)]

2. 확인 합니다 `TestCompletionCommandHandler` 클래스 구현 된 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> 인터페이스입니다.

     [!code-csharp[VSSDKCompletionTest#27](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_6.cs)]
     [!code-vb[VSSDKCompletionTest#27](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_6.vb)]

3. 에 `TestCompletionCommandHandlerProvider` 클래스, 가져오기는 <xref:Microsoft.VisualStudio.Text.Operations.ITextStructureNavigatorSelectorService>합니다.

     [!code-csharp[VSSDKCompletionTest#28](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_7.cs)]
     [!code-vb[VSSDKCompletionTest#28](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_7.vb)]

4. 코드 확장 인터페이스에 대 한 일부 개인 필드를 추가 및 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>합니다.

     [!code-csharp[VSSDKCompletionTest#29](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_8.cs)]
     [!code-vb[VSSDKCompletionTest#29](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_8.vb)]

5. 생성자에는 `TestCompletionCommandHandler` 클래스에 다음 필드를 설정 합니다.

     [!code-csharp[VSSDKCompletionTest#30](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_9.cs)]
     [!code-vb[VSSDKCompletionTest#30](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_9.vb)]

6. 클릭할 때 코드 조각 선택기를 표시 하는 **코드 조각 삽입** 명령에 다음 코드를 추가 합니다 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드. (이 설명의 가독성을 높일 있도록는 `Exec()`문 완성에 사용 되는 코드는 표시 되지 않으면 대신 코드 블록을 추가할 기존 메서드.) 다음 코드 블록은 문자를 확인 하는 코드 뒤에 추가 합니다.

     [!code-csharp[VSSDKCompletionTest#31](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_10.cs)]
     [!code-vb[VSSDKCompletionTest#31](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_10.vb)]

7. 코드 조각을 탐색할 수 있는 필드에 있는 경우 확장 세션 열기 때까지 유지 확장 명시적으로 허용 됩니다. 코드 조각에 필드가 없는 경우 세션을 닫고로 반환 됩니다 `null` 여는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionManager.InvokeInsertionUI%2A> 메서드. 에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드를 이전 단계에서 추가한 UI 코드 조각 선택 후 조각 탐색을 처리 하는 다음 코드를 추가 (사용자가 누르면 **탭** 또는 **Shift** + **탭** 조각 삽입 한 후).

     [!code-csharp[VSSDKCompletionTest#32](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_11.cs)]
     [!code-vb[VSSDKCompletionTest#32](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_11.vb)]

8. 사용자 형식 해당 바로 가기 키를 누를 때 코드 조각을 삽입할 **탭**, 코드를 추가 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.Exec%2A> 메서드. 코드 조각을 삽입 하는 private 메서드는 이후 단계에서 표시 됩니다. 이전 단계에서 추가한 탐색 코드 뒤에 다음 코드를 추가 합니다.

     [!code-csharp[VSSDKCompletionTest#33](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_12.cs)]
     [!code-vb[VSSDKCompletionTest#33](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_12.vb)]

9. 메서드를 구현 합니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient> 인터페이스입니다. 이 구현만 관련 메서드는 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.EndExpansion%2A> 고 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A>입니다. 다른 메서드는 반환 <xref:Microsoft.VisualStudio.VSConstants.S_OK>합니다.

     [!code-csharp[VSSDKCompletionTest#34](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_13.cs)]
     [!code-vb[VSSDKCompletionTest#34](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_13.vb)]

10. <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansionClient.OnItemChosen%2A> 메서드를 구현합니다. 실제로 확장을 삽입 하는 도우미 메서드는 이후 단계에서 다룹니다. 합니다 <xref:Microsoft.VisualStudio.TextManager.Interop.TextSpan> 에서 얻을 수 줄 및 열 정보를 제공 합니다 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextView>합니다.

     [!code-csharp[VSSDKCompletionTest#35](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_14.cs)]
     [!code-vb[VSSDKCompletionTest#35](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_14.vb)]

11. 다음 개인 메서드 바로 가기 또는 제목 및 경로 기반 코드 조각을 삽입 합니다. 그런 다음 호출 하 여 <xref:Microsoft.VisualStudio.TextManager.Interop.IVsExpansion.InsertNamedExpansion%2A> 조각 사용 하 여 메서드.

     [!code-csharp[VSSDKCompletionTest#36](../extensibility/codesnippet/CSharp/walkthrough-implementing-code-snippets_15.cs)]
     [!code-vb[VSSDKCompletionTest#36](../extensibility/codesnippet/VisualBasic/walkthrough-implementing-code-snippets_15.vb)]

## <a name="build-and-test-code-snippet-expansion"></a>빌드 및 테스트 코드 조각 확장
 코드 조각 확장 프로젝트에서 작동 하는지 테스트할 수 있습니다.

1. 솔루션을 빌드합니다. 디버거에서이 프로젝트를 실행 하면 Visual Studio의 두 번째 인스턴스를 시작 됩니다.

2. 텍스트 파일을 열고 일부 텍스트를 입력 합니다.

3. 텍스트의 위치를 마우스 오른쪽 단추로 누른 **코드 조각 삽입**합니다.

4. 포함 된 팝업을 사용 하 여 UI 같아야 합니다. 코드 조각 선택기 **테스트 대체 필드**합니다. 팝업을 두 번 클릭 합니다.

     다음 코드 조각은 삽입 되어야 합니다.

    ```
    MessageBox.Show("first");
    MessageBox.Show("second");
    ```

     키를 누르지 **Enter** 하거나 **Esc**합니다.

5. 키를 눌러 **탭** 하 고 **Shift**+**탭** "first" 및 "두 번째" 간에 설정/해제 합니다.

6. 눌러 삽입을 허용 **Enter** 하거나 **Esc**합니다.

7. 텍스트의 다른 부분에 "test"를 입력 한 다음 **탭**합니다. "Test" 코드 조각 바로 가기를 이기 때문에 코드 조각은 다시 삽입 해야 합니다.

## <a name="next-steps"></a>다음 단계
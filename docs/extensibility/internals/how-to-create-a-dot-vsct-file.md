---
title: '방법: 만들기는 합니다. Vsct 파일 | Microsoft Docs'
ms.date: 11/04/2016
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
author: madskristensen
ms.author: madsk
manager: jillfra
ms.workload:
- vssdk
ms.openlocfilehash: 95b085975a86db248517751fde7bd88c8bc2e35e
ms.sourcegitcommit: 40d612240dc5bea418cd27fdacdf85ea177e2df3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66328754"
---
# <a name="how-to-create-a-vsct-file"></a>방법: .Vsct 파일 만들기

Visual Studio XML 기반 명령 테이블 구성을 만들려면 여러 가지가 있습니다 ( *.vsct*) 파일입니다.

- 새 VSPackage를 만들 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지 템플릿.

- XML 기반 명령 테이블 구성 컴파일러를 사용할 수 있습니다 *Vsct.exe*, 기존 파일을 생성 하려면 *.ctc* 파일입니다.

- 사용할 수 있습니다 *Vsct.exe* 생성 하는 *.vsct* 기존 파일 *.cto* 파일입니다.

- 수동으로 만들 수 있습니다 새 *.vsct* 파일입니다.

  이 문서에서는 수동으로 새를 만드는 방법 설명 *.vsct* 파일입니다.

### <a name="to-manually-create-a-new-vsct-file"></a>새.vsct 파일을 수동으로 만들려면

1. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.

2. 에 **파일** 메뉴에서 **새로 만들기**를 클릭 하 고 **파일**합니다.

3. 에 **템플릿을** 창 클릭 **XML 파일** 클릭 하 고 **열기**합니다.

4. 에 **뷰** 메뉴에서 클릭 **속성** XML 파일의 속성을 표시 합니다.

5. 에 **속성** 창 클릭 합니다 **찾아보기** 단추를 **스키마** 속성입니다.

6. XSD 스키마의 목록에서 선택 합니다 *vsct.xsd* 스키마입니다. 목록에 없으면 클릭 **추가** 을 로컬 드라이브에 파일을 찾습니다. 클릭 **확인** 완료 되 면 합니다.

7. XML 파일에서 입력 *< CommandTable* 누릅니다 **탭**합니다. 입력 하 여 태그를 닫을 *>* 합니다.

    이 작업은 기본 만듭니다 *.vsct* 파일입니다.

8. 에 따라, 추가 하려는 XML 파일의 요소를 입력 합니다 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)합니다. 자세한 내용은 참조 하세요. [.vsct 파일 작성](../../extensibility/internals/authoring-dot-vsct-files.md)

<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>방법: 기존.ctc 파일에서.vsct 파일을 만들려면

XML 기반을 만들 수 있습니다 *.vsct* 파일에서 기존 명령 테이블 *.ctc* 소스 파일입니다. 이렇게 하면 새 XML 기반 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 테이블(VSCT) 컴파일러 형식을 이용할 수 있습니다.

### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>.ctc 파일에서 .vsct 파일을 만들려면

1. Perl 언어의 복사본을 가져옵니다.

2. Perl 스크립트의 복사본을 얻는 *ConvertCTCToVSCT.pl*이며 일반적으로  *\<Visual Studio SDK 설치 경로 > \VisualStudioIntegration\Tools\bin* 폴더입니다.

3. 복사본을 얻는 합니다 *.ctc* 변환 하려는 소스 파일입니다.

4. 동일한 디렉터리에 파일을 배치합니다.

5. 에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 프롬프트 창에서 디렉터리로 이동 합니다.

6. 형식

   ```
   perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct
   ```

    여기서 *PkgCmd.ctc* 의 이름입니다를 *.ctc* 파일 및 *PkgCmd.vsct* 의 이름인를 *.vsct* 만들려면 원하는 파일을 합니다.

    이 작업을 만듭니다 *.vsct* XML 명령 테이블 소스 파일이 있습니다. 사용 하 여 파일을 컴파일할 수 있습니다 *Vsct.exe*, VSCT 컴파일러인 것은 다른 *.vsct* 파일입니다.

   > [!NOTE]
   > 가독성을 향상 시킬 수 있습니다 합니다 *.vsct* XML 주석 다시 포맷 하는 파일입니다.

<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>방법: 기존.cto 파일에서.vsct 파일 만들기

XML 기반을 만들 수 있습니다 *.vsct* 파일을 기존 이진 *.cto* 파일입니다. 이렇게 하면 새 명령 테이블 컴파일러 형식을 이용할 수 있습니다. 경우에도이 프로세스 작동 합니다 *.cto* 파일에서 컴파일된를 *.ctc* 파일입니다. 편집 하 고 컴파일할 수는 *.vsct* 다른.cto 파일로 파일입니다.

### <a name="to-create-a-vsct-file-from-a-cto-file"></a>.cto 파일에서 .vsct 파일을 만들려면

1. 복사본을 가져옵니다 합니다 *.cto* 파일과 해당 *.ctsym* 파일입니다.

2. 동일한 디렉터리에 파일을 배치 합니다 *vsct.exe* 컴파일러.

3. Visual Studio 명령 프롬프트에서 포함 된 디렉터리로 이동 합니다 *.cto* 하 고 *.ctsym* 파일입니다.

4. 형식

    ```
    vsct.exe <ctofilename>.cto <vsctfilename>.vsct -S<symfilename>.ctsym
    ```

     여기서 \<ctofilename\> 의 이름입니다는 *.cto* 파일인 \<vsctfilename\> 의 이름인를 *.vsct* 파일을 만들려면 선택한 \<symfilename\> 이름인 합니다 *.ctsym* 파일입니다.

     이 프로세스를 만듭니다 *.vsct* XML 명령 테이블 컴파일러 파일입니다. 편집 하 고 사용 하 여 파일을 컴파일할 수 있습니다 *vsct.exe*, vsct 컴파일러인 것은 다른 *.vsct* 파일입니다.

## <a name="compile-the-code"></a>코드 컴파일
 추가 하기만 하면를 *.vsct* 파일을 프로젝트 컴파일 되도록 발생 하지 않습니다. 빌드 프로세스에 통합 해야 합니다.

### <a name="to-add-a-vsct-file-to-project-compilation"></a>프로젝트 컴파일으로.vsct 파일을 추가 하려면

1. 편집기에서 프로젝트 파일을 엽니다. 프로젝트 로드 되 면 먼저 언로드합니다 해야 있습니다.

2. 추가 [ItemGroup 요소](../../msbuild/itemgroup-element-msbuild.md) 포함 하는 `VSCTCompile` 요소를 다음 예제에서와 같이 합니다.

    ```xml
    <ItemGroup>
      <VSCTCompile Include="TopLevelMenu.vsct">
        <ResourceName>Menus.ctmenu</ResourceName>
      </VSCTCompile>
    </ItemGroup>

    ```

     합니다 `ResourceName` 요소는 항상으로 설정 `Menus.ctmenu`합니다.

3. 프로젝트에 포함 된 경우는 *.resx* 파일을 추가 `EmbeddedResource` 포함 하는 요소는 `MergeWithCTO` 다음 예제에서와 같이 요소:

    ```xml
    <EmbeddedResource Include="VSPackage.resx">
      <MergeWithCTO>true</MergeWithCTO>
      <ManifestResourceName>VSPackage</ManifestResourceName>
    </EmbeddedResource>

    ```

     이 태그 안에 있어야 합니다 `ItemGroup` 포함된 리소스를 포함 하는 요소입니다.

4. 이름은 일반적으로 패키지 파일을 엽니다  *\<ProjectName\>Package.cs* 하거나  *\<ProjectName\>Package.vb*, 편집기에서.

5. 추가 된 `ProvideMenuResource` 다음 예제에서와 같이 패키지 클래스에 특성입니다.

    ```csharp
    [ProvideMenuResource("Menus.ctmenu", 1)]
    ```

     첫 번째 매개 변수 값의 값과 일치 해야 합니다는 `ResourceName` 프로젝트 파일에 정의 된 특성입니다.

## <a name="see-also"></a>참고자료
- [.Vsct 파일 작성](../../extensibility/internals/authoring-dot-vsct-files.md)
- [Visual Studio 명령 테이블 (.vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
- [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)
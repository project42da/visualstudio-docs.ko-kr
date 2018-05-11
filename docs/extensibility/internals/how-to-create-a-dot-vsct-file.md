---
title: '방법: 만들기는 합니다. Vsct 파일 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSCT files, creating
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: c6456b0b866f08956862fa197719354bedf0ecf6
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="how-to-create-a-vsct-file"></a>방법: 만들기는 합니다. Vsct 파일  
  
여러 가지 방법으로 XML 기반 Visual Studio 명령 테이블 (.vsct) 구성 파일을 만듭니다.  
  
-   새 VSPackage를 만들 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지 템플릿을 합니다.  
  
-   기존.ctc 파일에서 파일을 생성 하려면 XML 기반 명령을 테이블 구성 컴파일러 Vsct.exe를 사용할 수 있습니다.  
  
-   기존.cto 파일에서.vsct 파일을 생성 하려면 Vsct.exe를 사용할 수 있습니다.  
  
-   새.vsct 파일을 수동으로 만들 수 있습니다.  
  
 이 항목에서는 새.vsct 파일을 수동으로 만드는 방법에 설명 합니다.  
  
### <a name="to-manually-create-a-new-vsct-file"></a>수동으로 새.vsct 파일을 만들려면  
  
1.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.  
  
2.  에 **파일** 메뉴에서 **새로**, 클릭 하 고 **파일**합니다.  
  
3.  에 **템플릿** 창에서 클릭 **XML 파일** 클릭 하 고 **열려**합니다.  
  
4.  에 **보기** 메뉴를 클릭 **속성 창** XML 파일의 속성을 표시 합니다.  
  
5.  에 **속성** 창 스키마 속성에서 찾아보기 (...) 단추를 클릭 합니다.  
  
6.  XSD 스키마의 목록에서 vsct.xsd 스키마를 선택 합니다. 목록에 없으면 클릭 **추가** 다음 로컬 드라이브에 파일을 찾습니다. 클릭 **확인** 완료 되 면 합니다.  
  
7.  XML 파일에 입력 `<CommandTable` 한 다음 탭 키를 누릅니다. 입력 하 여 태그를 닫을 `>`합니다.  
  
     기본.vsct 파일을 만듭니다.  
  
8.  추가 하려는 하는 XML 파일의 요소를 입력에 따라는 [VSCT 스키마](../../extensibility/vsct-xml-schema-reference.md)합니다. 자세한 내용은 참조 [제작 합니다. Vsct 파일](../../extensibility/internals/authoring-dot-vsct-files.md)  
  
<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-ctc-file"></a>방법: 기존 .Ctc 파일에서 .Vsct 파일 만들기  
  
기존 명령 테이블 .ctc 소스 파일에서 XML 기반 .vsct 파일을 만들 수 있습니다. 이 작업을 수행 하면 활용할 수 새 XML 기반 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 테이블 (VSCT) 컴파일러 형식을 합니다.  
  
### <a name="to-create-a-vsct-file-from-a-ctc-file"></a>.ctc 파일에서 .vsct 파일을 만들려면  
  
1.  Perl 언어의 복사본을 가져옵니다.  
  
2.  일반적으로에 있는 Perl 스크립트 ConvertCTCToVSCT.pl의 복사본을 가져올는  *\<Visual Studio SDK 설치 경로 >* \VisualStudioIntegration\Tools\bin 폴더입니다.  
  
3.  변환하려는 .ctc 소스 파일의 복사본을 가져옵니다.  
  
4.  동일한 디렉터리에 파일을 배치합니다.  
  
5.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 명령 프롬프트 창에서 디렉터리로 이동합니다.  
  
6.  형식  
  
    ```  
    perl.exe ConvertCTCtoVSCT.pl PkgCmd.ctc PkgCmd.vsct  
    ```  
  
     여기서 PkgCmd.ctc는 .ctc 파일의 이름이고 PkgCmd.vsct는 만들려는 .vsct 파일의 이름입니다.  
  
     이 경우 새 .vsct XML 명령 테이블 소스 파일이 생성됩니다. VSCT 컴파일러인 Vsct.exe를 사용하여 다른 .vsct 파일처럼 파일을 컴파일할 수 있습니다.  
  
    > [!NOTE]
    >  XML 주석의 형식을 다시 지정하여 .vsct 파일의 가독성을 향상시킬 수 있습니다.  
  
<a name="how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file"></a>

## <a name="how-to-create-a-vsct-file-from-an-existing-cto-file"></a>방법: 기존 .Cto 파일에서 .Vsct 파일 만들기  
  
기존 이진 .cto 파일에서 XML 기반 .vsct 파일을 만들 수 있습니다. 이렇게 하면 새 명령 테이블 컴파일러 형식을 이용할 수 있습니다. 이 프로세스는 .ctc 파일에서 .cto 파일이 컴파일된 경우에도 작동합니다. .vsct 파일을 편집하여 다른 .cto 파일로 컴파일할 수 있습니다.  
  
### <a name="to-create-a-vsct-file-from-a-cto-file"></a>.cto 파일에서 .vsct 파일을 만들려면  
  
1.  .cto 파일 및 해당 .ctsym 파일의 복사본을 가져옵니다.  
  
2.  vsct.exe 컴파일러와 같은 디렉터리에 파일을 배치합니다.  
  
3.  Visual Studio 명령 프롬프트에서 .cto 및 .ctsym 파일이 들어 있는 디렉터리로 이동합니다.  
  
4.  형식 **vsct.exe** *ctofilename * * *.cto** * vsctfilename ***.vsct-S***symfilename ***.ctsym**합니다.  
  
     `ctofilename` .cto 파일의 이름인 `vsctfilename` , 만들려는 vsct 파일의 이름 및 `symfilename` .ctsym 파일의 이름입니다.  
  
     이 프로세스는 새 .vsct XML 명령 테이블 컴파일러 파일을 만듭니다. vsct 컴파일러인 vsct.exe를 사용하여 다른 .vsct 파일처럼 파일을 편집 및 컴파일할 수 있습니다.  
  
## <a name="compiling-the-code"></a>코드 컴파일  
 프로젝트에.vsct 파일을 추가 하기만 하면 않을 컴파일하기 합니다. 빌드 프로세스에서 병합 해야 합니다.  
  
### <a name="to-add-a-vsct-file-to-project-compilation"></a>프로젝트 컴파일으로.vsct 파일을 추가 하려면  
  
1.  편집기에서 프로젝트 파일을 엽니다. 프로젝트가 로드 되는 경우 먼저 언로드할 해야 있습니다.  
  
2.  추가 [ItemGroup 요소](../../msbuild/itemgroup-element-msbuild.md) 다음 예제와 같이 VSCTCompile 요소를 포함 하는 합니다.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="TopLevelMenu.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
  
    ```  
  
     ResourceName 요소는 항상으로 설정 될 `Menus.ctmenu`합니다.  
  
3.  프로젝트에.resx 파일이 포함 된 경우 다음 예제와 같이 MergeWithCTO 요소를 포함 하는 포함 리소스 요소를 추가 합니다.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <ManifestResourceName>VSPackage</ManifestResourceName>  
    </EmbeddedResource>  
  
    ```  
  
     이 태그는 포함된 리소스가 들어 있는 ItemGroup 요소 안에 이동 해야 합니다.  
  
4.  이름은 일반적으로 패키지 파일을 엽니다 *ProjectName*Package.cs 또는 *ProjectName*Package.vb 편집기에서.  
  
5.  다음 예제와 같이 ProvideMenuResource 특성 패키지 클래스에 추가 합니다.  
  
    ```csharp  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    ```  
  
     첫 번째 매개 변수 값에는 프로젝트 파일에 정의 된 ResourceName 특성의 값과 일치 해야 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [제작 합니다. Vsct 파일](../../extensibility/internals/authoring-dot-vsct-files.md)   
 [Visual Studio 명령 테이블 (합니다. Vsct) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)
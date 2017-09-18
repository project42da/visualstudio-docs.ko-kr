---
title: "방법: 만들기는 합니다. Vsct 파일 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "VSCT 파일 만들기"
ms.assetid: b955f51c-f9f9-49c3-a8e4-63b6eb0e0341
caps.latest.revision: 19
caps.handback.revision: 19
ms.author: "gregvanl"
manager: "ghogen"
---
# 방법: 만들기는 합니다. Vsct 파일
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

여러 가지 방법을 통해 Visual Studio 명령 테이블 XML 기반 구성 \(.vsct\) 파일을 만듭니다.  
  
-   새 VSPackage에 만들 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 패키지 템플릿을 합니다.  
  
-   기존.ctc 파일에서 파일을 생성 하려면 Vsct.exe, XML 기반 명령 테이블 구성 컴파일러를 사용할 수 있습니다.  
  
-   기존.cto 파일에서.vsct 파일을 생성 하려면 Vsct.exe를 사용할 수 있습니다.  
  
-   새.vsct 파일을 수동으로 만들 수 있습니다.  
  
 이 항목에서는 새.vsct 파일을 수동으로 만드는 방법을 설명 합니다.  
  
### 새.vsct 파일을 수동으로 만들려면  
  
1.  [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 시작합니다.  
  
2.  에 **파일** 메뉴에서 **새로**, 를 클릭 하 고 **파일**합니다.  
  
3.  에 **템플릿** 창에서 클릭 **XML 파일** 클릭 하 고 **열려**합니다.  
  
4.  에 **보기** 메뉴 클릭 **속성 창** XML 파일의 속성을 표시 합니다.  
  
5.  에 **속성** 창에서 찾아보기 \(...\)를 클릭 합니다. 스키마 속성 단추입니다.  
  
6.  XSD 스키마 목록에서 vsct.xsd 스키마를 선택 합니다. 목록에 없으면 클릭 **추가** 다음 로컬 드라이브에 파일을 찾습니다. 클릭 **확인** 설치가 완료 되 면 합니다.  
  
7.  XML 파일에서 입력 `<CommandTable` 한 다음 탭 키를 누릅니다. 입력 하 여 태그를 닫을 `>`합니다.  
  
     기본.vsct 파일을 만듭니다.  
  
8.  추가할 XML 파일의 요소에 입력에 따라는 [VSCT 스키마](../../extensibility/vsct-xml-schema-reference.md)합니다. 자세한 내용은 [제작 합니다. Vsct 파일](../../extensibility/internals/authoring-dot-vsct-files.md)을 참조하세요.  
  
## 코드 컴파일  
 .Vsct 파일을 프로젝트에 추가 하기만 하면 발생 하지 않습니다 컴파일하기. 빌드 프로세스에 통합 해야 합니다.  
  
### 프로젝트 컴파일으로.vsct 파일을 추가 하려면  
  
1.  편집기에서 프로젝트 파일을 엽니다. 프로젝트가 로드 되는 경우 먼저 언로드할 해야 있습니다.  
  
2.  추가 [ItemGroup 요소](../../msbuild/itemgroup-element-msbuild.md) VSCTCompile 요소를 포함 하는 다음 예와에서 같이 합니다.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="TopLevelMenu.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
  
    ```  
  
     ResourceName 요소는 항상으로 설정 될 `Menus.ctmenu`합니다.  
  
3.  프로젝트가.resx 파일을 포함 하는 경우 다음 예와에서 같이 MergeWithCTO 요소를 포함 하는 포함 리소스 요소를 추가 합니다.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <ManifestResourceName>VSPackage</ManifestResourceName>  
    </EmbeddedResource>  
  
    ```  
  
     이 태그는 포함된 리소스를 포함 하는 ItemGroup 요소 안에 보내야 합니다.  
  
4.  이름은 일반적으로 패키지 파일을 열고 *ProjectName*Package.cs 또는 *ProjectName*편집기에서 Package.vb 합니다.  
  
5.  다음 예제와 같이 ProvideMenuResource 특성 패키지 클래스에 추가 합니다.  
  
    ```c#  
    [ProvideMenuResource("Menus.ctmenu", 1)]  
    ```  
  
     첫 번째 매개 변수 값은 프로젝트 파일에 정의 된 ResourceName 특성의 값을 일치 해야 합니다.  
  
## 참고 항목  
 [제작 합니다. Vsct 파일](../../extensibility/internals/authoring-dot-vsct-files.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [방법: 기존 .Ctc 파일에서 .Vsct 파일 만들기](../../misc/how-to-create-a-dot-vsct-file-from-an-existing-dot-ctc-file.md)   
 [방법: 기존 .Cto 파일에서 .Vsct 파일 만들기](../../misc/how-to-create-a-dot-vsct-file-from-an-existing-dot-cto-file.md)   
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)
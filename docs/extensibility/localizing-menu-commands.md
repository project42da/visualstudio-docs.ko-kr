---
title: "메뉴 명령 지역화 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- localize
- localization
- vsct
- menu commands
- localize visual studio
- localize vsct
ms.assetid: b04ee0f6-82ea-47e6-853a-72382267d6da
caps.latest.revision: 11
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 4a36302d80f4bc397128e3838c9abf858a0b5fe8
ms.openlocfilehash: 13910907c6041884cc0a1414fd0bfd82757a7639
ms.contentlocale: ko-kr
ms.lasthandoff: 09/26/2017

---
# <a name="localizing-menu-commands"></a>메뉴 명령 지역화
메뉴에 대 한 지역화 된 텍스트를 제공할 수 있습니다 및 도구 모음 지역화 된.vsct 파일을 작성 하 여 명령 및.resx 파일 VSPackage를 제거한 다음 프로젝트 파일을 업데이트 하 여 변경 내용을 통합에 대 한 지역화 합니다.  
  
 설치 경험을 지역화 하는 방법에 대 한 정보를 참조 하십시오. [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)합니다.  
  
## <a name="localizing-command-names"></a>명령 이름을 지역화  
 Vspackage, 메뉴 명령 및 도구 모음 단추.vsct 파일에서 정의 됩니다.  
  
1.  **솔루션 탐색기**에서.vsct 파일의 이름을 변경 *filename*에.vsct *filename*하는데.en-us.resources US.vsct 합니다.  
  
2.  사본을 *filename*하는데.en-us.resources US.vsct 각각에 대해 지역화 언어입니다.  
  
     각 복사본의 이름을 *filename*.* 로캘*.vsct, 여기서 *로캘* 특정 문화권 이름입니다. 문화권 이름 값의 목록에 대 한 참조 [Microsoft에서 할당 한 로캘 Id](https://msdn.microsoft.com/en-us/library/windows/apps/jj657969.aspx)합니다.  
  
     이러한 *filename*.* 로캘*.vsct 파일 패키지에 대 한 지역화 된 메뉴 텍스트에 포함 됩니다.  
  
3.  각각 열어 *filename*.* 로캘*.vsct 파일을 텍스트를 지역화 합니다.  
  
    1.  수정 된 [ButtonText](../extensibility/buttontext-element.md) 값 요소는 해당 언어에 적합 합니다.  
  
    2.  지역화 된 아이콘을 제공 하는 경우 수정 된 [비트맵](../extensibility/bitmap-element.md) 대상 파일을 가리키도록 값입니다.  
  
     다음 예제에서는 패밀리 트리 탐색기 도구 창을 열려면 명령에 대 한 영어와 스페인어 단추 텍스트를 보여 줍니다.  
  
     [FamilyTree.en US.vsct]  
  
    ```xml  
    <Button guid="guidLocalizedPackageCmdSet" id="cmdidFamilyTree" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <Icon guid="guidImages" id="bmpPic2" />  
      <Strings>  
        <CommandName>cmdidFamilyTree</CommandName>  
        <ButtonText>Family Tree Explorer</ButtonText>  
      </Strings>  
    </Button>  
    ```  
  
     [FamilyTree.es ES.vsct]  
  
    ```xml  
    <Button guid="guidLocalizedPackageCmdSet" id="cmdidFamilyTree" priority="0x0100" type="Button">  
      <Parent guid="guidSHLMainMenu" id="IDG_VS_WNDO_OTRWNDWS1"/>  
      <Icon guid="guidImages" id="bmpPic2" />  
      <Strings>  
        <CommandName>cmdidFamilyTree</CommandName>  
        <ButtonText>Explorar el arbol genealogico</ButtonText>  
      </Strings>  
    </Button>  
  
    ```  
  
## <a name="localizing-other-text-resources"></a>다른 텍스트 리소스 지역화  
 명령 이름 제외 텍스트 리소스는 리소스 (.resx) 파일에 정의 됩니다.  
  
1.  VSPackage.en US.resx VSPackage.resx의 이름을 바꿉니다.  
  
2.  지역화 된 언어 마다 VSPackage.en US.resx 파일의 복사본을 만듭니다.  
  
     각 복사본 VSPackage 이름을 지정 합니다. *로캘*.resx, 여기서 *로캘* 특정 문화권 이름입니다.  
  
3.  Resources.resx를 Resources.en US.resx 이름을 바꿉니다.  
  
4.  지역화 된 언어 마다 Resources.en US.resx 파일의 복사본을 만듭니다.  
  
     각 복사본 리소스 이름을 지정 합니다. *로캘*.resx, 여기서 *로캘* 특정 문화권 이름입니다.  
  
5.  특정 언어와 문화권에 맞게 문자열 값을 수정 하려면 각.resx 파일을 엽니다. 다음 예제에서는 도구 창의 제목 표시줄에 대 한 지역화 된 리소스 정을 보여 줍니다.  
  
     [Resources.en US.resx]  
  
    ```xml  
    <data name="ToolWindowTitle" xml:space="preserve">  
      <value>Family Tree Explorer</value>  
    </data>  
    ```  
  
     [Resources.es ES.resx]  
  
    ```xml  
    <data name="ToolWindowTitle" xml:space="preserve">  
      <value>Explorador del arbol genealogico</value>  
    </data>  
  
    ```  
  
## <a name="incorporating-localized-resources-into-the-project"></a>관리자는 프로젝트에 지역화 된 리소스를 통합  
 Assemblyinfo.cs 파일 및 지역화 된 리소스를 통합 하도록 프로젝트 파일을 수정 해야 합니다.  
  
1.  **속성** 노드에서 **솔루션 탐색기**, assemblyinfo.cs 또는 assemblyinfo.vb 편집기에서 엽니다.  
  
2.  다음 항목을 추가 합니다.  
  
    ```csharp  
    [assembly: NeutralResourcesLanguage("en-US", UltimateResourceFallbackLocation.Satellite)]  
    ```  
  
     이 설정 된 기본 언어로 영어 (미국) 합니다.  
  
3.  프로젝트를 언로드하십시오.  
  
4.  편집기에서 프로젝트 파일을 엽니다.  
  
5.  찾을 `ItemGroup` 포함 된 요소 `EmbeddedResource` 요소입니다.  
  
6.  에 `EmbeddedResource` VSPackage.en-US.resx를 호출 하는 요소를 대체는 `ManifestResourceName` 인 요소는 `LogicalName` 로 설정 하는 요소 `VSPackage.en-US.Resources`다음과 같이 합니다.  
  
    ```xml  
    <EmbeddedResource Include="VSPackage.en-US.resx">  
      <MergeWithCTO>true</MergeWithCTO>  
      <LogicalName>VSPackage.en-US.Resources</LogicalName>  
    </EmbeddedResource>  
    ```  
  
7.  지역화 된 각 언어에 대 한 복사는 `EmbeddedResource` VsPackage.en 미국 영어 및 설정에 대 한 요소는 **Include** 특성 및 **LogicalName** 요소 다음에 표시 된 대로 대상 로캘로 복사본의 예입니다.  
  
8.  지역화 된 각 `VSCTCompile` 요소를 추가 `ResourceName` 가리키는 요소의 `Menus.ctmenu`다음 예제에 나온 것 처럼 합니다.  
  
    ```xml  
    <ItemGroup>  
      <VSCTCompile Include="LocalizedPackage.es-ES.vsct">  
        <ResourceName>Menus.ctmenu</ResourceName>  
      </VSCTCompile>  
    </ItemGroup>  
    ```  
  
9. 프로젝트 파일을 저장 하 고 프로젝트를 다시 로드 합니다.  
  
10. 프로젝트를 빌드합니다.  
  
     주 어셈블리와 각 언어에 대 한 리소스 어셈블리를 만듭니다. 배포 프로세스를 지역화에 대 한 정보를 참조 하세요. [VSIX 패키지 지역화](../extensibility/localizing-vsix-packages.md)  
  
## <a name="see-also"></a>참고 항목  
 [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md)   
 [MenuCommand 및 OleMenuCommands](../extensibility/menucommands-vs-olemenucommands.md)   
 [응용 프로그램 전역화 및 지역화](../ide/globalizing-and-localizing-applications.md)

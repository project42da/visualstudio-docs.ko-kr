---
title: "솔루션 탐색기 도구 모음에는 명령을 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- toolbars [Visual Studio], adding buttons
- buttons [Visual Studio], adding to Solution Explorer
- Solution Explorer, adding buttons
ms.assetid: f6411557-2f4b-4e9f-b02e-fce12a6ac7e9
caps.latest.revision: "39"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 26f5777477617b0bffe008ec92873b852af8fe08
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="adding-a-command-to-the-solution-explorer-toolbar"></a>솔루션 탐색기 도구 모음에는 명령을 추가
이 연습에서는 단추를 추가 하는 방법을 보여 줍니다.는 **솔루션 탐색기** 도구 모음입니다.  
  
 도구 모음이 나 메뉴에 있는 모든 명령은 Visual Studio에서 단추를 라고 합니다. 단추를 클릭할 때 명령 처리기에서 코드가 실행 됩니다. 일반적으로 관련된 명령은 한 그룹을 구성 하기 위해 함께 그룹화 됩니다. 메뉴 또는 도구 모음에 대 한 컨테이너로 그룹입니다. 우선 순위는 그룹의 개별 명령을 메뉴 또는 도구 모음에 나타나는 순서를 결정 합니다. 단추의 표시 유형을 제어 하 여 도구 모음 또는 메뉴에 표시 되지 않도록 방지할 수 있습니다. 에 나열 된 명령을 `<VisibilityConstraints>` .vsct 파일의 섹션 연결 된 컨텍스트에만 나타납니다. 표시 여부는 그룹에 적용할 수 없습니다.  
  
 메뉴, 도구 모음 명령 및.vsct 파일에 대 한 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
> [!NOTE]
>  명령 테이블 (.ctc) 구성 파일 대신 XML 명령 테이블 (.vsct) 파일을 사용 하 여 사용자 Vspackage에서 메뉴 및 명령을 표시 하는 방법을 정의 합니다. 자세한 내용은 [Visual Studio Command Table (.Vsct) Files](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-an-extension-with-a-menu-command"></a>메뉴 명령을 사용 하 여 확장 만들기  
 라는 VSIX 프로젝트 `SolutionToolbar`합니다. 명명 된 메뉴 명령 항목 템플릿을 추가 **ToolbarButton**합니다. 이 작업을 수행 하는 방법에 대 한 정보를 참조 하십시오. [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
## <a name="adding-a-button-to-the-solution-explorer-toolbar"></a>솔루션 탐색기 도구 모음에 단추 추가  
 이 섹션의 연습 단추를 추가 하는 방법을 보여 줍니다는 **솔루션 탐색기** 도구 모음입니다. 단추를 클릭할 때 콜백 메서드에서 코드가 실행 됩니다.  
  
1.  ToolbarButtonPackage.vsct 파일에서 이동 하 여 `<Symbols>` 섹션. `<GuidSymbol>` 노드 메뉴 그룹 및 패키지 템플릿에 의해 생성 된 명령을 포함 합니다. 추가 `<IDSymbol>` 이 노드에 명령을 포함 하는 그룹을 선언 하는 요소입니다.  
  
    ```xml  
    <IDSymbol name="SolutionToolbarGroup" value="0x0190"/>  
    ```  
  
2.  에 `<Groups>` 섹션 후 기존 그룹 항목 정의 선언 하는 새 그룹 이전 단계에서 합니다.  
  
    ```xml  
    <Group guid="guidToolbarButtonPackageCmdSet"  
           id="SolutionToolbarGroup" priority="0xF000">  
            <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
          </Group>  
    ```  
  
     부모 guid: id 쌍을 설정 합니다. `guidSHLMainMenu` 및 `IDM_VS_TOOL_PROJWIN` 가이 그룹에는 **솔루션 탐색기** 우선 순위가 높은 값을 설정 하 고 도구 모음에서 다른 명령 그룹 후 넣습니다.  
  
3.  에 `<Buttons>` 섹션에서 생성 된 부모 ID를 변경 `<Button>` 항목을 이전 단계에서 정의 된 그룹을 반영 합니다. 수정 된 `<Button>` 요소는 다음과 같이 표시 됩니다.  
  
    ```xml  
    <Button guid="guidToolbarButtonPackageCmdSet" id="ToolbarButtonId" priority="0x0100" type="Button">  
        <Parent guid="guidToolbarButtonPackageCmdSet" id="SolutionToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPicStrikethrough" />  
        <Strings>  
            <ButtonText>Invoke ToolbarButton</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
4.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
     **솔루션 탐색기** 도구 모음 기존 단추 오른쪽에 새 명령 단추를 표시 합니다. 단추 아이콘 취소선입니다.  
  
5.  새로 만들기 단추를 클릭 합니다.  
  
     에 메시지가 있는 대화 상자 **ToolbarButtonPackage 내 SolutionToolbar.ToolbarButton.MenuItemCallback()** 표시 해야 합니다.  
  
## <a name="controlling-the-visibility-of-a-button"></a>단추의 표시 여부를 제어합니다.  
 이 연습 단원에서는 도구 모음 단추의 표시 여부를 제어 하는 방법을 보여 줍니다. 하나 이상의 프로젝트에는 컨텍스트를 설정 하 여는 `<VisibilityConstraints>` 섹션 SolutionToolbar.vsct 파일의 단추 모두 경우에 한 프로젝트 또는 프로젝트 열기를 제한할 수 있습니다.  
  
#### <a name="to-display-a-button-when-one-or-more-projects-are-open"></a>하나 이상의 프로젝트가 열려 있는 경우에 단추를 표시 하려면  
  
1.  에 `<Buttons>` 섹션 ToolbarButtonPackage.vsct의 두 개의 명령 플래그를 기존 추가 `<Button>` 요소 사이의 `<Strings>` 및 `<Icons>` 태그입니다.  
  
    ```xml  
    <CommandFlag>DefaultInvisible</CommandFlag>  
    <CommandFlag>DynamicVisibility</CommandFlag>  
    ```  
  
     `DefaultInvisible` 및 `DynamicVisibility` 플래그 설정 해야 하므로 해당 항목에는 `<VisibilityConstraints>` 섹션 내용을 적용 합니다.  
  
2.  만들기는 `<VisibilityConstraints>` 에 두 개의 섹션 `<VisibilityItem>` 항목입니다. 새 섹션 닫는 바로 뒤에 배치 `</Commands>` 태그입니다.  
  
    ```xml  
    <VisibilityConstraints>  
        <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
              id="ToolbarButtonId"  
              context="UICONTEXT_SolutionHasSingleProject" />  
        <VisibilityItem guid="guidToolbarButtonPackageCmdSet"  
              id="ToolbarButtonId"  
              context="UICONTEXT_SolutionHasMultipleProjects" />  
    </VisibilityConstraints>  
    ```  
  
     각 표시 유형 항목에는 지정한 단추가 표시 되는 조건을 나타냅니다. 여러 조건을 적용 하려면 같은 단추에 대 한 항목이 여러 개 만들어야 합니다.  
  
3.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 표시 됩니다.  
  
     **솔루션 탐색기** 도구 모음 취소선 단추를 포함 하지 않습니다.  
  
4.  프로젝트를 포함 하는 솔루션을 엽니다.  
  
     기존 단추 오른쪽에 도구 모음에 취소선 단추가 나타납니다.  
  
5.  에 **파일** 메뉴를 클릭 하 여 **솔루션 닫기**합니다. 단추가 도구 모음에서 사라집니다.  
  
 에 의해 제어 됩니다 단추의 표시 여부 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage 로드 될 때까지 합니다. VSPackage를 로드 한 다음 단추의 표시 여부는 VSPackage에서 제어 됩니다.  자세한 내용은 참조 [MenuCommands Vs. OleMenuCommands](../extensibility/menucommands-vs-olemenucommands.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)
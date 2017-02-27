---
title: "단추의 다시 사용할 수 있는 그룹 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Vspackage에서 만들기 단추 그룹"
  - "Vspackage를 다시 사용할 수 있는 단추 그룹 만들기"
  - "단추를 다시 사용할 수 있는 그룹 만들기"
ms.assetid: 0c561617-fb86-476d-8bd1-c6e5e7464c65
caps.latest.revision: 44
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 44
---
# 단추의 다시 사용할 수 있는 그룹 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

명령 그룹은 항상 함께 나타나는 메뉴 또는 도구 모음에 명령 모음입니다. .Vsct 파일의 CommandPlacements 섹션에 다른 부모 메뉴에 할당 하 여 모든 명령 그룹을 다시 사용할 수 있습니다.  
  
 명령 그룹에는 일반적으로 단추를 포함 하지만 다른 메뉴 또는 콤보 상자에도 포함 될 수 있습니다.  
  
### 단추의 다시 사용할 수 있는 그룹을 만들려면  
  
1.  라는 VSIX 프로젝트를 `ReusableButtons`합니다. 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)을 참조하십시오.  
  
2.  프로젝트를 열면 라는 사용자 지정 명령 항목 템플릿을 추가 **ReusableCommand**합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드, 명령 파일 이름을 **ReusableCommand.cs**합니다.  
  
3.  .Vsct 파일에서 기호 섹션으로 이동 하 고 그룹 및 프로젝트에 대 한 명령을 포함 하는 GuidSymbol 요소를 찾습니다. 그 이름은 guidReusableCommandPackageCmdSet 합니다.  
  
4.  다음 예제와 같이 그룹에 추가할 각 단추에 대 한 IDSymbol를 추가 합니다.  
  
    ```xml  
    <GuidSymbol name="guidReusableCommandPackageCmdSet" value="{7f383b2a-c6b9-4c1d-b4b8-a26dc5b60ca1}"> <IDSymbol name="MyMenuGroup" value="0x1020" /> <IDSymbol name="ReusableCommandId" value="0x0100" /> <IDSymbol name="SecondReusableCommandId" value="0x0200" /> </GuidSymbol>  
    ```  
  
     기본적으로 명령은 항목 템플릿을 만듭니다 이라는 그룹을 **MyGroup** 및 각각에 대 한 IDSymbol 항목이 함께 제공 된 이름이 있는 단추입니다.  
  
5.  그룹 섹션의 Symbols 섹션에 지정 된 것과 동일한 GUID 및 ID 특성을 가진 그룹 요소를 만듭니다. 기존 그룹을 사용 하거나 다음 예제 에서처럼 명령 템플릿에서 제공 되는 항목을 사용할 수도 있습니다. 이 그룹에 표시 된 **도구** 메뉴  
  
    ```xml  
    <Groups> <Group guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600"> <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS"/> </Group> </Groups>  
    ```  
  
### 다시 사용 하기 위해 여러 단추 그룹을 만들려면  
  
1.  명령이 나 메뉴 명령 또는 메뉴의 정의에 대 한 부모 그룹을 사용 하 여 또는 CommandPlacements 섹션을 사용 하 여 그룹의 명령이 나 메뉴를 배치 하 여 그룹에 넣을 수 있습니다.  
  
     단추 섹션에서 해당 부모 그룹에 있는 단추를 정의 하거나 패키지 템플릿을 제공 하는 단추를 사용 하 여 다음 예와에서 같이 합니다.  
  
    ```xml  
    <Button guid="guidReusableCommandPackageCmdSet" id="ReusableCommandId" priority="0x0100" type="Button"> <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" /> <Icon guid="guidImages" id="bmpPic1" /> <Strings> <ButtonText>Invoke ReusableCommand</ButtonText> </Strings> </Button>  
    ```  
  
2.  둘 이상의 그룹에는 단추가 표시 해야 하는 경우 항목을 만듭니다에 대 한 CommandPlacements 절의 명령 섹션 뒤에 배치 되어야 합니다. 단추를 배치 하려면 원하는 항목과 일치 하도록 CommandPlacement 요소의 GUID 및 ID 특성을 설정로 설정한 GUID 및 ID는 부모 요소의 대상 그룹의 다음 예제와 같이 합니다.  
  
    ```xml  
    <CommandPlacements> <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="SecondReusableCommandId" priority="0x105"> <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" /> </CommandPlacement> </CommandPlacements>  
    ```  
  
    > [!NOTE]
    >  새 명령 그룹에서 명령의 위치를 결정 하는 우선 순위 필드의 값입니다. 우선 순위 요소를 재정의 하는 항목 정의에 설정 된 CommandPlacement에서 설정 합니다. 낮은 우선 순위 값이 있는 명령은 더 높은 우선 순위 값이 있는 명령 앞에 표시 됩니다. 중복 된 우선 순위 값은 사용할 수 있지만 때문에 동일한 우선 순위 값을 가진 명령의 상대 위치를 보장할 수 없는 되는 순서는 **devenv \/setup** 최종 명령은 인터페이스 레지스트리에서 일관 되지 않을 수 있습니다.  
  
### 메뉴에 다시 사용할 수 있는 여러 단추 그룹을 저장 하려면  
  
1.  에 항목을 생성 된 `CommandPlacements` 섹션입니다. GUID 및 ID를 설정 합니다.는 `CommandPlacement` 요소 그룹의 GUID 및 ID의 대상 위치는 부모를 설정 합니다.  
  
     CommandPlacements 섹션 명령 섹션 바로 뒤 배치 해야 합니다.  
  
    ```xml  
    <CommandTable> ... <Commands>... </Commands> <CommandPlacements>... </CommandPlacements> ... </CommandTable>  
    ```  
  
     둘 이상의 메뉴 명령 그룹을 포함할 수 있습니다. 부모 메뉴 가능 만든 하나에서 제공 되는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] \(같이 설명 ShellCmdDef.vsct 또는 SharedCmdDef.vsct\), 또는 다른 VSPackage에 정의 된 하나입니다. 부모 메뉴에 연결 최종적으로 부모 계층의 수는 무제한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 또는 VSPackage로 표시 되는 바로 가기 메뉴에 있습니다.  
  
     다음 예제에서는 그룹에는 **솔루션 탐색기** 의 다른 단추 오른쪽에 있습니다.  
  
    ```xml  
    <CommandPlacements> <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0xF00"> <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/> </CommandPlacement> </CommandPlacements>  
    ```  
  
    ```xml  
    <CommandPlacements> <CommandPlacement guid="guidButtonGroupCmdSet" id="MyMenuGroup" priority="0x605"> <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS" /> </CommandPlacement> </CommandPlacements>  
  
    ```
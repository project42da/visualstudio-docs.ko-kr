---
title: 단추의 다시 사용할 수 있는 그룹 만들기 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- button groups, creating in VSPackages
- VSPackages, creating reusable button groups
- buttons, creating reusable groups
ms.assetid: 0c561617-fb86-476d-8bd1-c6e5e7464c65
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 97ee7cc2ec63a94036472ccce07b1dc9fa736504
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="creating-reusable-groups-of-buttons"></a>단추의 다시 사용할 수 있는 그룹 만들기
명령 그룹은 항상 메뉴 또는 도구 모음에 함께 표시 되는 명령 컬렉션입니다. 모든 명령 그룹.vsct 파일의 CommandPlacements 섹션에서 다른 부모 메뉴에 할당 하 여 다시 사용할 수 있습니다.  
  
 명령 그룹에는 일반적으로 단추를 포함 하지만 다른 메뉴 또는 콤보 상자에도 포함 될 수 있습니다.  
  
### <a name="to-create-a-reusable-group-of-buttons"></a>단추의 다시 사용할 수 있는 그룹을 만들려면  
  
1.  라는 VSIX 프로젝트 `ReusableButtons`합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
2.  프로젝트를 열 때 명명 된 사용자 지정 명령 항목 템플릿을 추가 **ReusableCommand**합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드에서 명령 파일 이름을 변경한 **ReusableCommand.cs**합니다.  
  
3.  .Vsct 파일에서 기호 섹션으로 이동 하 고 그룹 및 프로젝트에 대 한 명령을 포함 하는 GuidSymbol 요소를 찾습니다. 그 이름은 guidReusableCommandPackageCmdSet 합니다.  
  
4.  다음 예제와 같이 그룹에 추가할 각 단추에 대 한 IDSymbol를 추가 합니다.  
  
    ```xml  
    <GuidSymbol name="guidReusableCommandPackageCmdSet" value="{7f383b2a-c6b9-4c1d-b4b8-a26dc5b60ca1}">  
        <IDSymbol name="MyMenuGroup" value="0x1020" />  
        <IDSymbol name="ReusableCommandId" value="0x0100" />  
        <IDSymbol name="SecondReusableCommandId" value="0x0200" />  
    </GuidSymbol>  
    ```  
  
     명령 항목 템플릿에 기본적으로 명명 된 그룹을 만듭니다 **MyMenuGroup** 와 각각에 대 한 IDSymbol 항목이 함께 제공 된 이름이 있는 단추가 있습니다.  
  
5.  그룹 섹션에서 기호 섹션에서 제공 되는 것과 동일한 GUID 및 ID 특성을 지닌 그룹 요소를 만듭니다. 기존 그룹을 사용 하거나 다음 예제와 같이 명령 서식 파일에서 제공 되는 항목을 사용할 수도 있습니다. 이 그룹에 표시 된 **도구** 메뉴  
  
    ```xml  
    <Groups>  
        <Group guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
              <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS"/>  
        </Group>  
    </Groups>  
    ```  
  
### <a name="to-create-a-group-of-buttons-for-reuse"></a>다시 사용할 수 있도록 단추 그룹을 만들려면  
  
1.  명령이 나 메뉴 명령이 나 메뉴에서의 정의에 대 한 부모 그룹을 사용 하 여 또는 CommandPlacements 섹션을 사용 하 여 그룹의 명령이 나 메뉴를 배치 하 여 그룹에 넣을 수 있습니다.  
  
     단추 섹션에서 해당 부모와 사용자 그룹에 있는 단추를 정의 하거나 다음 예제와 같이 패키지 템플릿으로 제공 되는 단추를 사용 하 여 합니다.  
  
    ```xml  
    <Button guid="guidReusableCommandPackageCmdSet" id="ReusableCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke ReusableCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
2.  단추는 둘 이상의 그룹에 나타나야 합니다, 하는 경우 항목을 만듭니다에 대 한 CommandPlacements 절의 Commands 섹션 뒤에 배치 합니다. 를 배치 하려면 원하는 단추와 일치 하도록 CommandPlacement 요소의 GUID 및 ID 특성을 설정한 다음 설정 GUID 및 ID는 부모 요소의 대상 그룹의 다음 예제와 같이 합니다.  
  
    ```xml  
    <CommandPlacements>  
        <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="SecondReusableCommandId" priority="0x105">  
          <Parent guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" />  
        </CommandPlacement>  
    </CommandPlacements>  
    ```  
  
    > [!NOTE]
    >  새 명령 그룹에서 명령의 위치를 결정 하는 우선 순위 필드의 값입니다. 우선 순위 요소를 재정의 하는 항목 정의에 설정 된 CommandPlacement에서 설정 합니다. 낮은 우선 순위 값이 있는 명령은 더 높은 우선 순위 값이 있는 명령 앞에 표시 됩니다. 중복 우선 순위 값이 허용 되지만 때문에 동일한 우선 순위 값을 가진 명령의 상대 위치를 보장할 수 없는 되는 순서는 **devenv /setup** 명령은 레지스트리에서 최종 인터페이스를 만듭니다. 일관 되지 않을 수 있습니다.  
  
### <a name="to-put-a-reusable-group-of-buttons-on-a-menu"></a>메뉴에 다시 사용할 수 있는 단추 그룹을 저장 하려면  
  
1.  항목을 만들는 `CommandPlacements` 섹션. GUID 및 ID의 설정는 `CommandPlacement` 요소 그룹의 GUID 및 ID의 대상 위치로의 부모를 설정 합니다.  
  
     Commands 섹션에서는 바로 뒤 CommandPlacements 섹션을 배치 해야 합니다.  
  
    ```xml  
    <CommandTable>  
    ...  
      <Commands>... </Commands>  
      <CommandPlacements>... </CommandPlacements>  
    ...   
    </CommandTable>  
    ```  
  
     명령 그룹 둘 이상의 메뉴에 포함 시킬 수 있습니다. 부모 메뉴 가능 만든에서 제공 되는 하나 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] (같이에서 설명 ShellCmdDef.vsct 또는 SharedCmdDef.vsct), 다른 VSPackage에서 정의 된 또는 합니다. 부모 메뉴를 연결할 최종적으로 부모 계층의 수는 무제한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 또는 VSPackage에 표시 되는 바로 가기 메뉴에 있습니다.  
  
     는 그룹을 설정 하는 다음 예제는 **솔루션 탐색기** 의 다른 단추 오른쪽에 있습니다.  
  
    ```xml  
    <CommandPlacements>  
        <CommandPlacement guid="guidReusableCommandPackageCmdSet" id="MyMenuGroup" priority="0xF00">  
          <Parent guid="guidSHLMainMenu" id="IDM_VS_TOOL_PROJWIN"/>  
        </CommandPlacement>  
    </CommandPlacements>  
    ```  
  
    ```xml  
    <CommandPlacements>  
      <CommandPlacement guid="guidButtonGroupCmdSet" id="MyMenuGroup"   
          priority="0x605">  
        <Parent guid="guidSHLMainMenu" id="IDM_VS_MENU_TOOLS" />  
      </CommandPlacement>  
    </CommandPlacements>  
  
    ```

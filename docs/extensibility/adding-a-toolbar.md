---
title: "도구 모음 추가 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "도구 모음[Visual Studio], IDE에 추가"
  - "IDE, 도구 모음 추가"
ms.assetid: 17302c25-6f59-4e97-8c85-54f95336a07f
caps.latest.revision: 38
caps.handback.revision: 38
ms.author: "gregvanl"
manager: "ghogen"
---
# 도구 모음 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 Visual Studio IDE에 도구 모음을 추가 하는 방법을 보여 줍니다.  
  
 도구 모음은 명령에 바인딩되는 단추가 포함 된 가로 또는 세로 줄무늬입니다. 해당 구현에 따라 IDE의 도구 모음 위치를 변경할 주 IDE 창의 한쪽에 도킹 하거나 수 다른 창 앞에 유지 하려고 합니다.  
  
 사용자가 도구 모음에 명령을 추가 하거나 여기에서 사용 하 여 제거할 수 뿐만 아니라는 **사용자 지정** 대화 상자입니다. 일반적으로 Vspackage에는 도구 모음은 사용자를 사용자 지정할 수 있습니다. IDE에서 모든 사용자 지정을 처리 하 고 VSPackage 명령에 응답 합니다. VSPackage는 명령을 실제 위치를 알 필요가 없습니다.  
  
 메뉴에 대 한 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## 도구 모음을 사용 하 여 확장을 만들기  
 라는 VSIX 프로젝트를 `IDEToolbar`합니다. 명명 된 메뉴 명령 항목 템플릿을 추가 **ToolbarTestCommand**합니다. 이 작업을 수행 하는 방법에 대 한 정보를 참조 하십시오. [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
## IDE에 대 한 도구 모음 만들기  
  
1.  ToolbarTestCommandPackage.vsct, Symbols 섹션을 찾습니다. GuidToolbarTestCommandPackageCmdSet 라는 GuidSymbol 요소에는 도구 모음 및 도구 모음 그룹에 대 한 선언을 다음과 같이 추가 합니다.  
  
    ```xml  
    <IDSymbol name="Toolbar" value="0x1000" />  
    <IDSymbol name="ToolbarGroup" value="0x1050" />  
  
    ```  
  
2.  명령 섹션 맨 위에 있는 메뉴 섹션을 만듭니다. 도구 모음을 정의 하는 메뉴 섹션을 메뉴 요소를 추가 합니다.  
  
    ```xml  
    <Menus>  
        <Menu guid="guidToolbarTestCommandPackageCmdSet" id="Toolbar"  
            type="Toolbar" >  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
          </Menu>  
    </Menus>  
    ```  
  
     도구 모음 하위 메뉴와 같은 중첩 될 수 없습니다. 부모 그룹에 할당할 필요가 없습니다. 또한 않아도 우선 순위를 설정 하려면 도구 모음을 이동할 수 있으므로 합니다. 일반적으로 도구 모음의 초기 배치 프로그래밍 방식으로 정의 되었지만 사용자가 후속 변경 내용은 유지 됩니다.  
  
3.  에 [그룹](../extensibility/groups-element.md) 섹션 후 기존 그룹 항목을 정의 하는 [그룹](../extensibility/group-element.md) 도구 모음에 대 한 명령을 포함 하는 요소입니다.  
  
    ```xml  
    <Group guid="guidToolbarTestCommandPackageCmdSet" id="ToolbarGroup"  
          priority="0x0000">  
      <Parent guid="guidToolbarTestCommandPackageCmdSet" id="Toolbar"/>  
    </Group>  
    ```  
  
4.  확인 단추를 도구 모음에 표시 합니다. 단추 섹션의 도구 모음에 단추에 대 한 부모 블록을 교체 합니다. 완성 된 단추 블록은 다음과 같아야 합니다.  
  
    ```xml  
    <Button guid="guidToolbarTestCommandPackageCmdSet" id="ToolbarTestCommandId" priority="0x0100" type="Button">  
        <Parent guid= "guidToolbarTestCommandPackageCmdSet" id="ToolbarGroup" />  
                <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke ToolbarTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     기본적으로 도구 모음에 명령이 없는 경우 나타나지 않습니다.  
  
5.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 나타납니다.  
  
6.  도구 모음 목록을 가져오려면 Visual Studio 메뉴 모음을 마우스 오른쪽 단추로 클릭 합니다. 선택 **테스트 도구 모음**합니다.  
  
7.  이제에서 찾기 아이콘 파일의 오른쪽에 아이콘으로 도구 모음에 표시 됩니다. 아이콘을 클릭 하면 알리는 메시지 상자가 표시 됩니다 **ToolbarTestCommandPackage. IDEToolbar.ToolbarTestCommand.MenuItemCallback\(\) 내**합니다.  
  
## 참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)
---
title: "도구 창에는 도구 모음 추가 | Microsoft Docs"
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
  - "도구 창, 도구 모음 추가"
  - "도구 모음 [Visual Studio] 도구 창에 추가"
ms.assetid: 172f64b3-87f8-4292-9c1c-65bffa2b0970
caps.latest.revision: 48
caps.handback.revision: 46
ms.author: "gregvanl"
manager: "ghogen"
---
# 도구 창에는 도구 모음 추가
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에는 도구 창 도구 모음을 추가 하는 방법을 보여 줍니다.  
  
 도구 모음은 명령에 연결 하는 단추가 포함 된 가로 또는 세로 줄무늬입니다. 도구 창의 도구 모음의 길이와 너비 또는 높이의 도구 창 도구 모음 도킹 될 위치에 따라 항상 같습니다.  
  
 IDE에서 도구 모음, 달리 도구 창에서 도구 모음 해야 도킹 및 이동 하거나 수 없습니다 사용자 지정 합니다. VSPackage umanaged 코드에서를 작성 한 경우 도구 모음에서 모든 가장자리에 도킹 될 수 있습니다.  
  
 도구 모음을 추가 하는 방법에 대 한 자세한 내용은 참조 [도구 모음 추가](../extensibility/adding-a-toolbar.md)합니다.  
  
## 사전 요구 사항  
 이 연습을 수행하려면 Visual Studio SDK를 설치해야 합니다. 자세한 내용은 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)을 참조하세요.  
  
## 도구 창에 대 한 도구 모음 만들기  
  
1.  라는 이름의 VSIX 프로젝트 `TWToolbar` 모두 라는 메뉴 명령이 있는 **TWTestCommand** 및 명명 된 도구 창 **TestToolWindow**합니다. 자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md) 및 [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)를 참조하세요. 도구 창 서식 파일을 추가 하기 전에 명령 항목 템플릿을 추가 해야 합니다.  
  
2.  TWTestCommandPackage.vsct, Symbols 섹션을 찾습니다. GuidTWTestCommandPackageCmdSet GuidSymbol 노드에서 다음과 같이 도구 모음 및 도구 모음 그룹을 선언 합니다.  
  
    ```xml  
    <IDSymbol name="TWToolbar" value="0x1000" />  
    <IDSymbol name="TWToolbarGroup" value="0x1050" />  
    ```  
  
3.  맨 위에 있는 `Commands` 섹션을 만듭니다는 `Menus` 섹션입니다. 추가 `Menu` 도구 모음을 정의 하는 요소입니다.  
  
    ```xml  
    <Menus>  
        <Menu guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" type="ToolWindowToolbar">  
            <CommandFlag>DefaultDocked</CommandFlag>  
            <Strings>  
                <ButtonText>Test Toolbar</ButtonText>  
                <CommandName>Test Toolbar</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     도구 모음 하위 메뉴와 같은 중첩 될 수 없습니다. 따라서 부모를 할당할 필요가 없습니다. 또한 않아도 우선 순위를 설정 하려면 도구 모음을 이동할 수 있으므로 합니다. 일반적으로 도구 모음의 초기 배치 프로그래밍 방식으로 정의 되었지만 사용자가 후속 변경 내용은 유지 됩니다.  
  
4.  그룹 섹션에서 도구 모음에 대 한 명령을 포함 하는 그룹을 정의 합니다.  
  
    ```xml  
  
    <Group guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" priority="0x0000">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbar" />  
    </Group>  
    ```  
  
5.  단추 섹션에서 기존 단추 요소의 부모 도구 모음 그룹 있도록 변경 도구 모음 표시 됩니다.  
  
    ```xml  
    <Button guid="guidTWTestCommandPackageCmdSet" id="TWTestCommandId" priority="0x0100" type="Button">  
        <Parent guid="guidTWTestCommandPackageCmdSet" id="TWToolbarGroup" />  
        <Icon guid="guidImages" id="bmpPic1" />  
        <Strings>  
            <ButtonText>Invoke TWTestCommand</ButtonText>  
        </Strings>  
    </Button>  
    ```  
  
     기본적으로 도구 모음에 명령이 없는 경우 나타나지 않습니다.  
  
     새 도구 모음 도구 창으로 자동으로 추가 되지 않기 때문 도구 모음을 명시적으로 추가 되어야 합니다. 이에 대해서는 다음 섹션에서 설명합니다.  
  
## 도구 모음 창에 추가 도구  
  
1.  TWTestCommandPackageGuids.cs에 다음 줄을 추가 합니다.  
  
    ```c#  
    public const string guidTWTestCommandPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const int TWToolbar = 0x1000;  
    ```  
  
2.  TestToolWindow.cs에서 다음 추가 문을 사용 합니다.  
  
    ```c#  
    using System.ComponentModel.Design;  
    ```  
  
3.  TestToolWindow 생성자에서 다음 줄을 추가 합니다.  
  
    ```c#  
    this.ToolBar = new CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), TWTestCommandPackageGuids.TWToolbar);  
    ```  
  
## 도구 창에서 도구 모음에서 테스트  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio의 실험적 인스턴스가 나타납니다.  
  
2.  에 **보기 \/ 다른 창** 메뉴 클릭 **테스트 도구 창** 도구 창을 표시 합니다.  
  
     도구 창의 제목 바로 아래 왼쪽 맨 위에 있는 \(다음과 같이 기본 아이콘\) 도구 모음 표시 됩니다.  
  
3.  도구 모음에서 메시지를 표시 하려면 아이콘을 클릭 **TWTestCommandPackage 내 TWToolbar.TWTestCommand.MenuItemCallback\(\)**합니다.  
  
## 참고 항목  
 [도구 모음 추가](../extensibility/adding-a-toolbar.md)
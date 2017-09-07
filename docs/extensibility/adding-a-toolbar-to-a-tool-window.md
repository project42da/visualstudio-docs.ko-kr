---
title: "도구 창에는 도구 모음 추가 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- tool windows, adding toolbars
- toolbars [Visual Studio], adding to tool windows
ms.assetid: 172f64b3-87f8-4292-9c1c-65bffa2b0970
caps.latest.revision: 48
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
ms.openlocfilehash: b094a04a9d2e273418edaa7cc4bc2d36f89e9d29
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="adding-a-toolbar-to-a-tool-window"></a>도구 창에는 도구 모음 추가
이 연습에서는 도구 창으로 도구 모음을 추가 하는 방법을 보여 줍니다.  
  
 도구 모음은 단추 명령에 바인딩된 포함 하는 수평 또는 수직 스트립입니다. 도구 창에서 도구 모음의 길이 항상 너비 또는 높이 도구 창의 도구 모음 도킹 될 위치에 따라와 동일 합니다.  
  
 IDE에서 도구 모음, 달리 도구 창에서 도구 모음 해야 도킹 될 및 없습니다 이동 하거나 사용자 지정 합니다. Umanaged 코드를 VSPackage를 작성 하는 경우 도구 모음에서 모든 가장자리에 도킹 될 수 있습니다.  
  
 도구 모음을 추가 하는 방법에 대 한 자세한 내용은 참조 [도구 모음 추가](../extensibility/adding-a-toolbar.md)합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-toolbar-for-a-tool-window"></a>도구 창에 대 한 도구 모음 만들기  
  
1.  라는 VSIX 프로젝트를 `TWToolbar` 라는 두는 메뉴 명령이 있는 **TWTestCommand** 및 도구 창이 **TestToolWindow**합니다. 자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md) 및 [도구 창을 사용 된 확장을 만드는](../extensibility/creating-an-extension-with-a-tool-window.md)합니다. 도구 창 서식 파일을 추가 하기 전에 명령 항목 템플릿을 추가 해야 합니다.  
  
2.  TWTestCommandPackage.vsct, 기호 섹션을 찾습니다. GuidTWTestCommandPackageCmdSet 라는 GuidSymbol 노드에 도구 모음 및 도구 모음 그룹을 다음과 같이 선언 합니다.  
  
    ```xml  
    <IDSymbol name="TWToolbar" value="0x1000" />  
    <IDSymbol name="TWToolbarGroup" value="0x1050" />  
    ```  
  
3.  맨 위에 있는 `Commands` 섹션을 만듭니다는 `Menus` 섹션. 추가 `Menu` 도구 모음을 정의 하는 요소입니다.  
  
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
  
     하위 메뉴와 같은 도구 모음을 중첩할 수 없습니다. 따라서 부모 할당할 필요가 없습니다. 또한 않아도 우선 순위를 설정 하려면 도구 모음을 이동할 수 있으므로 합니다. 일반적으로 도구 모음의 초기 배치 프로그래밍 방식으로 정의 되었지만 사용자가 후속 변경 내용은 유지 됩니다.  
  
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
  
     기본적으로 도구 모음에 명령이 없고이 나타나지 않습니다.  
  
     새 도구 모음 도구 창으로 자동으로 추가 되지 않기 때문에 도구 모음을 명시적으로 추가 합니다. 이에 대해서는 다음 섹션에서 설명합니다.  
  
## <a name="adding-the-toolbar-to-the-tool-window"></a>도구 창에 도구 모음 추가  
  
1.  TWTestCommandPackageGuids.cs 다음 줄을 추가 합니다.  
  
    ```csharp  
    public const string guidTWTestCommandPackageCmdSet = "00000000-0000-0000-0000-0000";  // get the GUID from the .vsct file  
    public const int TWToolbar = 0x1000;  
    ```  
  
2.  TestToolWindow.cs에 다음 추가 문을 사용 하 여 합니다.  
  
    ```csharp  
    using System.ComponentModel.Design;  
    ```  
  
3.  TestToolWindow 생성자에 다음 줄을 추가 합니다.  
  
    ```csharp  
    this.ToolBar = new CommandID(new Guid(TWTestCommandPackageGuids.guidTWTestCommandPackageCmdSet), TWTestCommandPackageGuids.TWToolbar);  
    ```  
  
## <a name="testing-the-toolbar-in-the-tool-window"></a>도구 창에서 도구 모음에서 테스트  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. Visual Studio 실험적 인스턴스 표시 되어야 합니다.  
  
2.  에 **보기 / 다른 창** 메뉴에서 클릭 **테스트 ToolWindow** 도구 창을 표시 합니다.  
  
     제목 바로 아래 도구 창의 왼쪽 맨 위에 있는 (같이 기본 아이콘) 도구 모음 표시 됩니다.  
  
3.  도구 모음에서 메시지를 표시할 아이콘을 클릭 **TWTestCommandPackage 내 TWToolbar.TWTestCommand.MenuItemCallback()**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [도구 모음 추가](../extensibility/adding-a-toolbar.md)

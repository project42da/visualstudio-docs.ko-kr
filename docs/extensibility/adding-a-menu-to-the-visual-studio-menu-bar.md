---
title: "Visual Studio 메뉴 모음에 메뉴를 추가합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "메뉴, 최상위 수준 만들기"
  - "최상위 메뉴"
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
caps.latest.revision: 51
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 51
---
# Visual Studio 메뉴 모음에 메뉴를 추가합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

이 연습에서는 Visual Studio 통합된 개발 환경 \(IDE\)의 메뉴 모음에 메뉴를 추가 하는 방법을 보여 줍니다. IDE의 메뉴 모음에서 메뉴 범주를와 같은 포함 **파일**, **편집**, **보기**, **창**, 및 **도움말**합니다.  
  
 Visual Studio 메뉴 모음에 새 메뉴를 추가 하기 전에 기존 메뉴 내 명령을 배치 해야 하는지 여부를 하는 것이 좋습니다. 명령 배치에 대 한 자세한 내용은 참조 [메뉴와 Visual Studio 명령](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md)합니다.  
  
 메뉴는 프로젝트의.vsct 파일에 선언 됩니다. 메뉴 및.vsct 파일에 대 한 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
 이 연습을 완료 하 여 명명 된 메뉴를 만들 수 있습니다 **TestMenu** 하나의 명령에 포함 된 합니다.  
  
## 사전 요구 사항  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램의 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)을 참조하세요.  
  
## 사용자 지정 명령 항목 템플릿이 있는 VSIX 프로젝트 만들기  
  
1.  라는 VSIX 프로젝트를 `TopLevelMenu`합니다. VSIX 프로젝트 템플릿을 찾을 수는 **새 프로젝트** 대화 상자의 **Visual C\#** \/ **확장성**합니다.  자세한 내용은 [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)을 참조하세요.  
  
2.  프로젝트를 열면 라는 사용자 지정 명령 항목 템플릿을 추가 **TestCommand**합니다. 에 **솔루션 탐색기**, 프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 \/ 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서 이동 **Visual C\# \/ 확장성** 선택한 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드, 명령 파일 이름을 **TestCommand.cs**합니다.  
  
## IDE의 메뉴 모음에서 메뉴 만들기  
  
#### 메뉴를 만들려면  
  
1.  **솔루션 탐색기**, TestCommandPackage.vsct를 엽니다.  
  
     파일의 끝에 여러 \< GuidSymbol \> 노드가 포함 된 \< 기호 \> 노드입니다. 노드에서 guidTestCommandPackageCmdSet 라는 새 기호를 다음과 같이 추가 합니다.  
  
    ```xml  
    <IDSymbol name="TopLevelMenu" value="0x1021"/>  
    ```  
  
2.  \< 명령 \> 노드 \< 그룹 \> 바로 앞에 빈 \< 메뉴 \> 노드를 만듭니다. \< 메뉴 \> 노드에 다음과 같이 \< 메뉴 \> 노드를 추가 합니다.  
  
    ```xml  
    <Menus>  
          <Menu guid="guidTestCommandPackageCmdSet" id="TopLevelMenu" priority="0x700" type="Menu">  
            <Parent guid="guidSHLMainMenu"  
                    id="IDG_VS_MM_TOOLSADDINS" />  
            <Strings>  
              <ButtonText>TestMenu</ButtonText>  
              <CommandName>TestMenu</CommandName>  
            </Strings>  
        </Menu>  
    </Menus>  
    ```  
  
     `guid` 및 `id` 명령 집합에 명령 집합 및 특정 메뉴를 지정 하는 메뉴의 값입니다.  
  
     `guid` 및 `id` 부모 값의 메뉴에서 도구와 추가 기능을 포함 하는 Visual Studio 메뉴 모음에는 메뉴의 위치입니다.  
  
     값은 `CommandName` 문자열 텍스트 메뉴 항목에 표시 되도록 지정 합니다.  
  
3.  \< 그룹 \> 섹션에서 \< 그룹 \> 찾을 방금 추가한 메뉴를 가리키도록 \< 부모 \> 요소를 변경 합니다.  
  
    ```c#  
    <Groups>  
          <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
            <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>  
          </Group>  
        </Groups>  
    ```  
  
     이렇게 하면 새 메뉴 그룹 부분이 있습니다.  
  
4.  찾기는 `Buttons` 섹션입니다. 다음에 유의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지 템플릿을 생성 한 `Button` 로 설정 하는 해당 부모를 가진 요소를 `MyMenuGroup`합니다. 결과적으로,이 명령이 메뉴에 나타납니다.  
  
## 빌드 및 확장 테스트  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스에서의 인스턴스로 표시 되어야 합니다.  
  
2.  실험적 인스턴스에서 메뉴 모음 있어야는 **TestMenu** 메뉴.  
  
3.  에 **TestMenu** 메뉴를 클릭 하 여 **테스트 명령 호출**합니다.  
  
     메시지 상자 표시 하 고 "TestCommand 패키지 내 TopLevelMenu.TestCommand.MenuItemCallback\(\)" 메시지를 표시 해야 합니다. 이 새 명령을 작동 한다는 것을 나타냅니다.  
  
## 참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)
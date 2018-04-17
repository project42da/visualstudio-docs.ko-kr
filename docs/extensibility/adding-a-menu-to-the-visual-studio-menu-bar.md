---
title: Visual Studio 메뉴 모음에 메뉴를 추가 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- menus, creating top level
- top-level menus
ms.assetid: 58fc1a31-2aeb-441c-8e48-c7d5cbcfe501
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 3a391da85c38176d79a1c77ce8836ce510e8d27e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="adding-a-menu-to-the-visual-studio-menu-bar"></a>Visual Studio 메뉴 모음에 메뉴 추가
이 연습에서는 Visual Studio 통합된 개발 환경 (IDE)의 메뉴 모음에 메뉴를 추가 하는 방법을 보여 줍니다. IDE의 메뉴 모음에서 메뉴 범주를와 같은 포함 **파일**, **편집**, **보기**, **창**, 및 **도움말** .  
  
 Visual Studio 메뉴 모음에 새 메뉴에 추가 하기 전에 기존 메뉴 내에서 명령을 배치 해야 하는지 여부를 하는 것이 좋습니다. 명령 배치에 대 한 자세한 내용은 참조 [메뉴와 Visual Studio 명령](../extensibility/ux-guidelines/menus-and-commands-for-visual-studio.md)합니다.  
  
 메뉴는 프로젝트의.vsct 파일에서 선언 됩니다. 메뉴 및.vsct 파일에 대 한 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
 이 연습을 완료 하 여 명명 된 메뉴를 만들 수 있습니다 **TestMenu** 명령 하나를 포함 하 합니다.  
  
## <a name="prerequisites"></a>필수 조건  
 Visual Studio 2015를 시작 하면 설치 하지 마십시오 Visual Studio SDK 다운로드 센터에서. Visual Studio 설치 프로그램에서 선택적 기능으로 포함 됩니다. 또한 VS SDK를 나중에 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="creating-a-vsix-project-that-has-a-custom-command-item-template"></a>사용자 지정 명령 항목 템플릿을 VSIX 프로젝트 만들기  
  
1.  라는 VSIX 프로젝트 `TopLevelMenu`합니다. VSIX 프로젝트 템플릿을 찾을 수 있습니다는 **새 프로젝트** 대화 상자의 **Visual C#** / **확장성**합니다.  자세한 내용은 참조 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
2.  프로젝트를 열 때 명명 된 사용자 지정 명령 항목 템플릿을 추가 **TestCommand**합니다. 에 **솔루션 탐색기**프로젝트 노드를 마우스 오른쪽 단추로 클릭 하 고 선택 **추가 / 새 항목**합니다. 에 **새 항목 추가** 대화 상자에서로 이동 **Visual C# / 확장성** 선택 **사용자 지정 명령**합니다. 에 **이름** 창의 맨 아래에 필드에서 명령 파일 이름을 변경한 **TestCommand.cs**합니다.  
  
## <a name="creating-a-menu-on-the-ide-menu-bar"></a>IDE의 메뉴 모음에서 메뉴 만들기  
  
#### <a name="to-create-a-menu"></a>메뉴를 만들려면  
  
1.  **솔루션 탐색기**, TestCommandPackage.vsct를 엽니다.  
  
     파일 끝에는 한 \<기호 > 여러 포함 된 노드 \<GuidSymbol > 노드. GuidTestCommandPackageCmdSet 명명 된 노드에 새 기호를 다음과 같이 추가 합니다.  
  
    ```xml  
    <IDSymbol name="TopLevelMenu" value="0x1021"/>  
    ```  
  
2.  빈 만들기 \<메뉴 >의 노드는 \<명령 > 노드를 직전 \<그룹 > 합니다. 에 \<메뉴 > 노드를 추가 \<메뉴 > 노드를 다음과 같이 합니다.  
  
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
  
     `guid` 및 `id` 명령 집합에서 명령 집합 및 특정 메뉴를 지정 하는 메뉴의 값입니다.  
  
     `guid` 및 `id` 부모의 값 메뉴의 도구 및 추가 기능 메뉴를 포함 하는 Visual Studio 메뉴 모음 섹션에 맞춰져 위치를 지정 합니다.  
  
     값은 `CommandName` 문자열 텍스트는 메뉴 항목에 표시 되도록 지정 합니다.  
  
3.  에 \<그룹 > 섹션에서 찾을 \<그룹 > 변경 하 고는 \<부모 > 방금 추가한 메뉴를 가리키도록 요소:  
  
    ```csharp  
    <Groups>  
          <Group guid="guidTestCommandPackageCmdSet" id="MyMenuGroup" priority="0x0600">  
            <Parent guid="guidTestCommandPackageCmdSet" id="TopLevelMenu"/>  
          </Group>  
        </Groups>  
    ```  
  
     이렇게 하면 새 메뉴의 그룹 부분입니다.  
  
4.  찾기의 `Buttons` 섹션. 에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 패키지 템플릿을 벌어 들인는 `Button` 로 설정 하는 해당 부모를 가진 요소를 `MyMenuGroup`합니다. 결과적으로,이 명령이 메뉴에 나타납니다.  
  
## <a name="building-and-testing-the-extension"></a>빌드 및 확장 테스트  
  
1.  프로젝트를 빌드하고 디버깅을 시작합니다. 실험적 인스턴스가 인스턴스 표시 되어야 합니다.  
  
2.  실험적 인스턴스 메뉴 모음 있어야는 **TestMenu** 메뉴.  
  
3.  에 **TestMenu** 메뉴를 클릭 하 여 **테스트 명령 호출**합니다.  
  
     메시지 상자를 표시 하 고 "TestCommand 패키지 내 TopLevelMenu.TestCommand.MenuItemCallback()" 메시지를 표시 해야 합니다. 이 새로운 명령이 작동 하는 것을 나타냅니다.  
  
## <a name="see-also"></a>참고 항목  
 [명령, 메뉴 및 도구 모음](../extensibility/internals/commands-menus-and-toolbars.md)
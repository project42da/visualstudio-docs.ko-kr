---
title: "메뉴 항목에 바로 가기 키 바인딩 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- keyboard command
- keyboards
- command key
- keyboard shortcuts
- menu items
ms.assetid: 19f483b6-4d3e-424e-9d68-dc129c788e47
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 1fe1c0bb9c3028c70e1be9df9af1de3b0804844e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="binding-keyboard-shortcuts-to-menu-items"></a>메뉴 항목에 바인딩 바로 가기 키
바로 가기 키 사용자 지정 메뉴 명령에 바인딩할 방금.vsct 파일 패키지에 대 한 항목을 추가 합니다. 이 기본 편집기에서 키보드 매핑을 적용 하거나 사용자 지정 편집기를 제한 하는 방법과 사용자 지정 단추, 메뉴 항목 또는 도구 모음 명령에 바로 가기 키를 매핑하는 방법을 설명 합니다.  
  
 바로 가기 키를 기존 Visual Studio 메뉴 항목에 할당 하려면 참조 [식별 및 사용자 지정 바로 가기 키](../ide/identifying-and-customizing-keyboard-shortcuts-in-visual-studio.md)합니다.  
  
## <a name="choosing-a-key-combination"></a>키 조합 선택  
 대부분의 키보드 바로 가기는 Visual Studio에서 이미 사용 됩니다. 할당 하면 안 같은 바로 가기 명령 하나 이상에 때문 이므로 한 중복 바인딩은 발견 하기 어려운 예기치 않은 결과가 발생할 수 있습니다. 따라서 할당 하기 전에 바로 가기의 가용성을 확인 하는 것이 좋습니다.  
  
#### <a name="to-verify-the-availability-of-a-keyboard-shortcut"></a>바로 가기 키의 가용성을 확인 하려면  
  
1.  에 **도구 / 옵션 / 환경** 창에서 **키보드**합니다.  
  
2.  다음 사항을 확인 **에서 새 바로 가기를 사용 하 여** 로 설정 된 **Global**합니다.  
  
3.  에 **바로 가기 키 누르기** 상자를 사용 하려는 바로 가기 키를 입력 합니다.  
  
     Visual Studio에서 바로 가기를 이미 사용 되는 경우는 **에서 현재 사용 하는 바로 가기** 상자 바로 가기 현재 호출 하는 명령에 표시 됩니다.  
  
4.  찾을 때까지 매핑되지 않은 다른 키 조합을 시도 합니다.  
  
    > [!NOTE]
    >  Alt 키를 사용 하는 바로 가기 키 메뉴 열고 명령을 직접 실행 될 수 있습니다. 따라서는 **에서 현재 사용 하는 바로 가기** alt 키를 포함 하 여 바로 가기를 입력 상자가 비어 있을 수 있습니다. 닫아 바로 가기 메뉴가 열립니다 하지 않는 것을 확인할 수 있습니다는 **옵션** 대화 상자와 다음 키를 누르면 됩니다.  
  
 다음 절차에서는 메뉴 명령 사용 하 여 기존 VSPackage는 있다고 가정 합니다. 이렇게 하면 각 도움이 필요한 경우에 대해 살펴봅니다 [메뉴 명령을 사용 하 여 확장을 만드는](../extensibility/creating-an-extension-with-a-menu-command.md)합니다.  
  
#### <a name="to-assign-a-keyboard-shortcut-to-a-command"></a>명령에 바로 가기 키를 지정 하려면  
  
1.  패키지에 대 한.vsct 파일을 엽니다.  
  
2.  빈 만들기 `<KeyBindings>` 이후 섹션에서 `<Commands>` 이미 존재 하지 않는 경우.  
  
    > [!WARNING]
    >  키 바인딩에 대 한 자세한 내용은 참조 하십시오. [Keybinding](../extensibility/keybinding-element.md)합니다.  
  
     에 `<KeyBindings>` 섹션을 만듭니다는 `<KeyBinding>` 항목입니다.  
  
     설정의 `guid` 및 `id` 호출 하려는 명령의 특성입니다.  
  
     설정의 `mod1` 특성을 **제어**, **Alt**, 또는 **Shift**합니다.  
  
     KeyBindings 섹션에는 다음과 같이 표시 됩니다.  
  
    ```xml  
    <KeyBindings>  
        <KeyBinding guid="<name of command set>" id="<name of command id>"  
            editor="guidVSStd97" key1="1" mod1="CONTROL"/>  
    </KeyBindings>  
  
    ```  
  
 바로 가기 두 개 이상의 키가 필요한 경우 설정의 `mod2` 및 `key2` 특성입니다.  
  
 대부분의 경우에서 **Shift** 이미를 눌러 대부분 영숫자 키 대문자 또는 기호를 입력 하기 때문에 두 번째 한정자 없이 사용 하지 않아야 합니다.  
  
 예를 들어 기능 키 그와 관련 된 문자를 갖지 않는 특수 키에 액세스할 가상 키 코드 수 및 **백스페이스** 키입니다. 자세한 내용은 참조 [가상 키 코드](http://go.microsoft.com/fwlink/?LinkID=105932)합니다.  
  
 명령을 사용 하려면 Visual studio에서 편집기 설정의 `editor` 특성을 `guidVSStd97`합니다.  
  
 명령을 사용자 지정 편집기 에서만 사용할 수 있게 하려면 설정는 `editor` 특성에서 생성 된 사용자 지정 편집기의 이름으로는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage를 만들 때 패키지 템플릿을 사용자 지정 편집기를 포함 합니다. 이름 값을 찾으려면 찾는 위치는 `<Symbols>` 섹션는 `<GuidSymbol>` 노드 인 `name` 특성으로 끝나는 "`editorfactory`." 사용자 지정 편집기의 이름입니다.  
  
## <a name="example"></a>예제  
 이 예에서는 명명 된 명령에 바로 가기 키 CTRL + ALT + C를 바인딩합니다 `cmdidMyCommand` 라는 패키지에서 `MyPackage`합니다.  
  
```  
<CommandTable>  
. . .  
<Commands>  
. . .  
</Commands>  
<KeyBindings>  
  <KeyBinding guid="guidMyPackageCmdSet" id="cmdidMyCommand"   
      key1="C" mod1="CONTROL" mod2="ALT" editor="guidVSStd97" />  
</KeyBindings>  
. . .  
</CommandTable>  
```  
  
## <a name="example"></a>예제  
 이 예에서는 명명 된 명령에 바로 가기 키 CTL + B를 바인딩합니다 `cmdidBold` 라는 프로젝트에서 `TestEditor`합니다. 다른 편집기 아니라 사용자 지정 편집기에만 명령을 ´ ù.  
  
```xml  
<KeyBinding guid="guidVSStd97" id="cmdidBold" editor="guidTestEditorEditorFactory" key1="B" mod1="Control" />  
```  
  
## <a name="see-also"></a>참고 항목  
 [메뉴 및 명령 확장](../extensibility/extending-menus-and-commands.md)
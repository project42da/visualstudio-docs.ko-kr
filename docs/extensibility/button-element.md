---
title: "요소 단추 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Buttons element (VSCT XML schema)
- VSCT XML schema elements, Buttons
ms.assetid: 96dccf51-2b00-4700-9d28-924b34c21ecd
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 5af5dce3edf1ac2910af5f8d593ed8e316cff721
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="button-element"></a>Button 요소
사용자와 상호 작용할 수 있는 요소를 정의 합니다. 다른 종류의 단추 수: 단추, MenuButton, 및 SplitDropDown 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Button guid="guidMyCommandSet" id="MyCommand" priority="0x102" type="button">  
  <Parent>... </Parent>  
  <Icon>... </Icon>  
  <CommandFlag>... </CommandFlag>  
  <Strings>... </Strings>  
</Button>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
  
|특성|설명|  
|---------------|-----------------|  
|guid|필수. GUID/ID 명령 식별자의 GUID입니다.|  
|ID|필수. ID는 GUID/ID 명령 식별자입니다.|  
|priority|선택 사항입니다. 우선 순위를 지정 하는 숫자 값입니다.|  
|type|선택 사항입니다. 단추 종류를 지정 하는 열거형된 값입니다.<br /><br /> 를 지정 하지 않으면 단추를 사용 합니다.<br /><br /> 단추<br /> 메뉴 및 상황에 맞는 메뉴 (일반적으로 아이콘 단추로) 도구 모음에 표시 되는 표준 명령입니다.<br /><br /> MenuButton<br /> 메뉴 항목 명령 실행 되지는 않지만 다른 메뉴를 생성 합니다.<br /><br /> SplitDropDown<br /> Microsoft Word에서 표준 도구 모음에서 실행 취소 및 다시 실행 단추와 같은 컨트롤입니다.|  
|조건|선택 사항입니다. 참조 [조건부 특성](../extensibility/vsct-xml-schema-conditional-attributes.md)합니다.|  
  
### <a name="child-elements"></a>자식 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Parent 요소](../extensibility/parent-element.md)|선택 사항입니다. 단추의 부모 요소입니다.|  
|[Icon 요소](../extensibility/icon-element.md)|선택 사항입니다. 단추와 연결 된 아이콘입니다.|  
|[Command Flag 요소](../extensibility/command-flag-element.md)|필수. 단추에 대 한 유효한 CommandFlag 값은 다음과 같습니다.<br /><br /> -AllowParams<br /><br /> -CommandWellOnly<br /><br /> -DefaultDisabled<br /><br /> -DefaultInvisible<br /><br /> -DontCache<br /><br /> -DynamicItemStart<br /><br /> -DynamicVisibility<br /><br /> -FixMenuController<br /><br /> -IconAndText<br /><br /> -NoButtonCustomize<br /><br /> -NoCustomize<br /><br /> -NoKeyCustomize<br /><br /> -NoShowOnMenuController<br /><br /> -Pict<br /><br /> -PostExec<br /><br /> -ProfferedCmd<br /><br /> -RouteToDocs<br /><br /> -TextCascadeUseBtn<br /><br /> -TextMenuUseButton<br /><br /> -TextChanges<br /><br /> -TextChangesButton<br /><br /> -TextContextUseButton<br /><br /> -TextMenuCtrlUseMenu<br /><br /> -TextMenuUseButton<br /><br /> -TextOnly|  
|[Strings 요소](../extensibility/strings-element.md)|필수. 자식 [ButtonText 요소](../extensibility/buttontext-element.md) 정의 해야 합니다.|  
|주석|선택적 설명입니다.|  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|[Buttons 요소](../extensibility/buttons-element.md)|단추 요소를 그룹화합니다.|  
  
## <a name="example"></a>예  
 다음 예제에서는.vsct 파일에서 단추를 정의 합니다.  

 ```xml
<Button guid="guidMenuTextCmdSet" id="cmdidMyCommand" priority="0x0100" type="Button">
    <Parent guid="guidMenuTextCmdSet" id="MyMenuGroup" />
    <Icon guid="guidImages" id="bmpPic1" />
    <CommandFlag>TextChanges</CommandFlag>
    <Strings>
          <CommandName>cmdidMyCommand</CommandName>
          <ButtonText>My Command name</ButtonText>
    </Strings>
</Button>
 ```
 
## <a name="see-also"></a>참고 항목  
 [Visual Studio 명령 테이블(.Vsct) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
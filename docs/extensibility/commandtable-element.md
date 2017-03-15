---
title: "CommandTable 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CommandTable"
helpviewer_keywords: 
  - "CommandTable 요소 (VSCT XML 스키마)"
  - "VSCT XML 스키마 요소, CommandTable"
ms.assetid: 15c38159-660a-4ef4-9643-aa6fcfca82a9
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# CommandTable 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

CommandTable는.vsct 파일의 루트 요소입니다. VSPackage IDE를 제공 하는 명령의 종류와 실제 레이아웃을 정의 하는 파일입니다. 명령 메뉴 항목, 메뉴, 도구 모음 및 콤보 상자에 포함 될 수 있습니다. 자세한 내용은 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)을 참조하세요.  
  
## 구문  
  
```  
<CommandTable xmlns="http://schemas.microsoft.com/VisualStudio/2005-10-18/CommandTable" xmlns:xs="http://www.w3.org/2001/XMLSchema" >  
  <Extern>... </Extern>  
  <Include>... </Include>  
  <Define>... </Define>  
  <Commands>... </Commands>  
  <CommandPlacements>... </CommandPlacements>  
  <VisibilityConstraints>... </VisibilityConstraints>  
  <KeyBindings>... </KeyBindings>  
  <UsedCommands... </UsedCommands>  
  <Symbols>... </Symbols>  
</CommandTable>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
  
|특성|설명|  
|--------|--------|  
|xmlns|필수 요소. XML 네임 스페이스:<br /><br /> xmlns \= "http:\/\/schemas.microsoft.com\/VisualStudio\/2005\-10\-18\/CommandTable"<br /><br /> xmlns:xs \= "http:\/\/www.w3.org\/2001\/XMLSchema"|  
|language|선택적 요소. 명령 테이블에서 모든 \< 문자열 \> 요소의 기본 언어를 지정 하는 언어 특성을 사용할 수 있습니다.  언어를 지정 하지 않으면 현재 프로세스의 언어가 사용 됩니다.<br /><br /> language \= "en\-us"|  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[Extern 요소](../extensibility/extern-element.md)|선택적 요소. 컴파일러에 대 한 전처리기 지시문을 포함합니다.|  
|[요소를 포함 합니다.](../extensibility/include-element.md)|선택적 요소. 컴파일에 포함할 모든 파일에 대 한 경로 포함 합니다.|  
|[요소를 정의 합니다.](../extensibility/define-element.md)|선택적 요소. 지정 된 이름과 값 기호를 정의 합니다.|  
|[Commands 요소](../extensibility/commands-element.md)|선택적 요소. 부모 요소를 다른 요소를 모두 포함 된 VSPackage에 대 한 모든 명령 정의입니다.|  
|[CommandPlacements 요소](../extensibility/commandplacements-element.md)|선택적 요소. 명령 모음에서 명령이 있는 올 수를 정의 합니다.|  
|[VisibilityConstraints 요소](../extensibility/visibilityconstraints-element.md)|선택적 요소. 명령 및 도구 모음 정적 표시 여부를 결정 합니다.|  
|[키 바인딩 요소](../extensibility/keybindings-element.md)|선택적 요소. 명령에 대 한 바로 가기 키 조합을 지정 합니다.|  
|[UsedCommands 요소](../extensibility/usedcommands-element.md)|선택적 요소. VSPackage를 선택적으로 자체 버전의 다른 Vspackage에서 원래 지원 기능을 구현할 수 있습니다.|  
|[Symbols Element](http://msdn.microsoft.com/ko-kr/f2ddd0aa-c3dd-439e-834d-28f136a27ffa)|선택적 요소. 컴파일러에 대 한\-Guid, Id 등\-모든 기호 데이터를 포함 합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|없음||  
  
## 참고 항목  
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
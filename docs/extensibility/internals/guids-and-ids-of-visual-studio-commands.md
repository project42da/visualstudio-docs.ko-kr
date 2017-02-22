---
title: "Guid 및 Visual Studio 명령 Id | Microsoft Docs"
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
  - "명령"
  - "ID"
  - "명령 배치"
  - "visual studio 명령"
  - "guid"
ms.assetid: 2ea4bee2-0259-4675-8e65-2023b312b516
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# Guid 및 Visual Studio 명령 Id
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

Visual Studio 통합된 개발 환경 \(IDE\) 포함 된 명령 GUID 및 ID 값 Visual Studio SDK의 일부로 설치 된.vsct 파일에 정의 됩니다.  자세한 내용은 [IDE 정의 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)를 참조하십시오.  
  
 .Vsct 파일에 정의 된 IDE 개체를 사용 하는 방법에 대 한 자세한 내용은 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md).  
  
## 명령 정의 찾기  
 1000 개 이상의 명령을 Visual Studio 정의 하기 때문에 여기서 모든 사용자를 나열 하는 것입니다.  대신, 명령에 대 한 정의 찾을 수 있는이 단계를 수행 하십시오.  
  
#### 명령 정의 찾으려면  
  
1.  Visual Studio 다음 파일을 열고를  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Common\\Inc\\ 폴더: SharedCmdDef.vsct, ShellCmdDef.vsct, VsDbgCmdUsed.vsct, Venusmenu.vsct.  
  
     Visual Studio 명령은 대부분의 SharedCmdDef.vsct 및 Shellcmddef.vsct에서 정의 됩니다.  VsDbgCmdUsed.vsct 디버거에서에 관련 된 명령을 정의 하 고 웹 개발에 관련 된 명령 venusmenu.vsct를 정의 합니다.  
  
2.  정확한 텍스트는 메뉴 항목의 명령 메뉴 항목인 경우 note입니다.  명령 단추는 도구 모음의 경우에 일시 중지 하는 경우 표시 되는 도구 설명 텍스트를 note입니다.  
  
3.  CTRL \+ F를 눌러 엽니다의  **찾을** 대화 상자.  
  
4.  에 있는  **찾을 내용** 상자에서 2 단계에서 적어 둔 텍스트를 입력 합니다.  
  
5.  확인  **모든 열린 문서** 에 표시 되는  **찾는 위치** 상자.  
  
6.  클릭는  **다음 찾기** 텍스트에서 선택 될 때까지 단추는 `<Strings>` 섹션에는 [Button 요소](../../extensibility/button-element.md).  
  
     `<Button>` 명령에 표시 되는 요소는 명령을 정의 합니다.  
  
 명령 정의 찾을 수 있을 때 사용자 명령 사본을 다른 메뉴나 도구 모음에서 작성 하 여 넣을 수 있습니다는 [CommandPlacement 요소](../../extensibility/commandplacement-element.md) 과 가진 `guid` 및 `id` 명령으로 값입니다.  자세한 내용은 [단추의 다시 사용할 수 있는 그룹 만들기](../../extensibility/creating-reusable-groups-of-buttons.md)를 참조하십시오.  
  
### 특별 한 경우  
 다음과 같은 경우에 텍스트 메뉴 또는 도구 설명 텍스트 정확 하 게 이란 명령을 정의에 일치 될 수 있습니다.  
  
-   같이 밑줄된 문자를 포함 하는 메뉴 항목을  **인쇄** 에  **파일** P 밑줄이 표시 되는 메뉴에서.  
  
     표시 메뉴 항목 이름에는 '&' 문자 앞에 문자에 밑줄이 있습니다.  그러나.vsct 파일 '&' 문자를 사용 하 여 특수 문자를 표시 하 고 표시 되는 앰퍼샌드로 철자 해야 것이 필요는 XML로 작성 된 ' & a m p;'.  따라서.vsct 파일에에서는  **P**인쇄 명령을 표시 하는 ' & a m p;인쇄 '.  
  
-   동적 텍스트를 가진 명령  **저장** *현재 파일 이름*, 및 동적 생성 된 항목 같은 메뉴 항목에는  **최근 파일** 목록입니다.  
  
     동적 텍스트를 검색할 수 있는 안정적인 방법이 없습니다.  대신, 원하는 명령 참조 하 여 호스트 그룹을 찾습니다 [Guid 및 Id의 Visual Studio 메뉴](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md) 또는 [Guid 및 Visual Studio 도구 모음의 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md), 및 그룹의 ID 검색 합니다.  명령 정의 그룹으로 하지 않는 경우 해당 [부모 요소](../../extensibility/parent-element.md), SharedCmdPlace.vsct 및 ShellCmdPlace.vsct \(또는 VsDbgCmdPlace.vsct 디버거 명령에 대 한\)에 대 한 검색은 `<CommandPlacement>` 명령의 부모를 설정 하는 요소.  에 SharedCmdPlace.vsct, ShellCmdPlace.vsct, Andvsdbgcmdplace.vsct는  *Visual Studio SDK 설치 경로가*\\VisualStudioIntegration\\Common\\Inc\\ 폴더입니다.  
  
## 참고 항목  
 [MenuCommand 및 OleMenuCommand](../../misc/menucommands-vs-olemenucommands.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)   
 [VSCT XML 스키마 참조](../../extensibility/vsct-xml-schema-reference.md)
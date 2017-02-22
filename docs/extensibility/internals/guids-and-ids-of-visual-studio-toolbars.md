---
title: "Guid 및 Visual Studio 도구 모음의 Id | Microsoft Docs"
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
  - "visual studio 그룹"
  - "도구 모음"
  - "visual studio 도구 모음"
  - "ID"
  - "toolgar 그룹"
  - "도구 창 도구 모음"
  - "guid"
ms.assetid: c9cacd57-9225-450f-a9ac-cbf3168ea844
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# Guid 및 Visual Studio 도구 모음의 Id
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 항목에서는 GUID 및 ID 값 Visual Studio 통합된 개발 환경 \(IDE\)에 포함 된 도구 모음을 열거 하 고 그룹을 포함 합니다.  이러한 값은 Visual Studio SDK의 일부로 설치 된.vsct 파일에 정의 됩니다.  자세한 내용은 [IDE 정의 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)를 참조하십시오.  
  
> [!NOTE]
>  대부분의 Visual Studio 사용할 수 Visual Studio 해당 GUID가 정의 되지 않은 및 ID 값은 공개 되지 않습니다.  이 항목에서는 Visual Studio SDK.vsct 파일에 정의 된 도구 모음만을 나열 합니다.  
  
 .Vsct 파일에 정의 된 IDE 개체를 사용 하는 방법에 대 한 자세한 내용은 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md).  
  
 GUID를 사용 하는 Visual Studio IDE에서 제공 하는 기본 도구 모음 `guidSHLMainMenu`, GUID:ID 구문을 사용 하 여 지정 하는 경우를 제외 하 고.  
  
## IDE 도구 모음  
 Visual Studio IDE에서 다음 도구 모음을 제공 합니다.  도구 모음을 선택 하 여 표시할 수 있습니다의  **도구 모음** 의 하위 메뉴의  **도구** 메뉴.  도구 창 도구 모음이이 섹션에 포함 되지 않습니다.  
  
 그룹 에서만 도구 모음에서 직접 내려가 야 수 있습니다.  그룹을 추가 하려면 부모 GUID 및 도구 모음의 ID를 설정 합니다.  도구 모음에 단추를 추가 하려면 도구 모음에서 그룹에 부모를 설정 합니다.  
  
|도구 모음|ID|  
|-----------|--------|  
|Standard|IDM\_VS\_TOOL\_STANDARD|  
|Build|IDM\_VS\_TOOL\_BUILD|  
|텍스트 편집기|IDM\_VS\_TOOL\_TEXTEDITOR|  
|디버그|guidVSDebugGroup:IDM\_DEBUG\_TOOLBAR|  
|디버그 위치|guidVSDebugGroup:IDM\_DEBUG\_CONTEXT\_TOOLBAR|  
  
### 특수 도구 모음  
 이러한 도구 모음은 Visual Studio IDE에서 정의 되지만 특수 한 기능을 수행 하 고 명령 그룹을 호스트 하지 않습니다.  
  
|도구 모음|ID|  
|-----------|--------|  
|추가 명령|IDM\_VS\_TOOL\_ADDCOMMAND|  
|정의되어 있지 않습니다.|IDM\_VS\_TOOL\_UNDEFINED|  
|XML 스키마|IDM\_VS\_TOOL\_SCHEMA|  
|XML 데이터|IDM\_VS\_TOOL\_DATA|  
  
## IDE 도구 모음에 그룹  
 표준 도구 모음에 단추를 추가 하려면 상위 다음 그룹 중 하나를 설정 합니다.  그룹 부모 도구 모음에서 정렬 됩니다.  
  
### 표준 도구 모음의 그룹  
  
|Name|ID|  
|----------|--------|  
|저장\/열기|IDG\_VS\_TOOLSB\_SAVEOPEN|  
|잘라내기\/붙여넣기|IDG\_VS\_TOOLSB\_CUTCOPY|  
|실행 취소\/다시 실행|IDG\_VS\_TOOLSB\_UNDOREDO|  
|실행\/구축|IDG\_VS\_TOOLSB\_RUNBUILD|  
|검색|IDG\_VS\_TOOLSB\_SEARCH|  
|Windows|IDG\_VS\_TOOLSB\_WINDOWS|  
|새 창|IDG\_VS\_TOOLSB\_NEWWINDOWS|  
|로드\/저장|IDG\_VS\_WINDOWUI\_LOADSAVE|  
|진행 상태 표시|IDG\_VS\_TOOLSB\_GAUGE|  
  
### 도구 모음 그룹 작성  
  
|Name|ID|  
|----------|--------|  
|빌드 모음|IDG\_VS\_BUILDBAR|  
|Cancel|IDG\_VS\_BUILD\_CANCEL|  
  
### 텍스트 편집기 도구 모음 그룹  
  
|Name|ID|  
|----------|--------|  
|완료|IDM\_VS\_TOOL\_TEXTEDITOR|  
|들여쓰기|IDG\_VS\_EDITTOOLBAR\_INDENT|  
|주석|IDG\_VS\_EDITTOOLBAR\_COMMENT|  
|책갈피|IDG\_VS\_EDITTOOLBAR\_TEMPBOOKMARKS|  
  
### 디버그 도구 모음 그룹  
  
|Name|ID|  
|----------|--------|  
|실행|IDM\_DEBUG\_TOOLBAR|  
|단계별 실행|IDG\_DEBUG\_TOOLBAR\_STEPPING|  
|Watch|IDG\_DEBUG\_TOOLBAR\_WATCH|  
|Windows|IDG\_DEBUG\_TOOLBAR\_WINDOWS|  
  
### 디버그 위치 도구 모음의 그룹  
  
|Name|ID|  
|----------|--------|  
|디버그 위치|IDG\_DEBUG\_CONTEXT\_TOOLBAR|  
  
## 도구 창 도구 모음  
 도구 모음이 나타날 수 있습니다 직접 IDE 나 도구 창 등  **솔루션 탐색기**.  도구 창 도구 모음 도구 창을.vsct 파일에 정의 되어 있지 않으므로 정의 된 부모가 없습니다.  대신, 이러한 코드에 배치 됩니다.  다음 표에서 IDE에서 도구 창에 나타나는 도구 모음 및 명령 그룹을 포함 보여 줍니다.  
  
> [!NOTE]
>  도구 모음 및 그룹 GUID를 사용 `guidSHLMainMenu`, GUID:ID 구문을 사용 하 여 지정 하는 경우를 제외 하 고.  도구 모음에 대 한 GUID를 지정 하는 경우 또한 해당 도구 모음에서 내려가 야 하는 그룹에 적용 됩니다.  
  
|도구 창|도구 모음|그룹|  
|----------|-----------|--------|  
|솔루션 탐색기|IDM\_VS\_TOOL\_PROJWIN|IDG\_VS\_PROJ\_TOOLBAR1.5|  
|서버 탐색기|guid\_SE\_MenuGroup:IDM\_SE\_TOOLBAR\_SERVEREXPLORER|IDG\_SE\_TOOLBAR\_REFRESH|  
|속성|IDM\_VS\_TOOL\_PROPERTIES|IDG\_VS\_PROPERTIES\_SORT<br /><br /> IDG\_VS\_PROPERTIES\_PAGES|  
|클래스 뷰|IDM\_VS\_TOOL\_CLASSVIEW|IDG\_VS\_CLASSVIEW\_FOLDERS<br /><br /> IDG\_VS\_CLASSVIEW\_SEARCH<br /><br /> IDG\_VS\_CLASSVIEW\_SETTINGS|  
|클래스 뷰|IDM\_VS\_TOOL\_CLASSVIEW\_GO|IDG\_VS\_CLASSVIEW\_SEARCH2|  
|개체 브라우저|IDM\_VS\_TOOL\_OBJBROWSER|IDG\_VS\_OBJBROWSER\_SUBSETS<br /><br /> IDG\_VS\_OBJBROWSER\_SEARCH<br /><br /> IDG\_VS\_OBJBROWSER\_ADDREFERENCE<br /><br /> IDG\_VS\_OBJBROWSER\_BROWSERSETTINGS|  
|개체 브라우저|IDM\_VS\_TOOL\_OBJECT\_BROWSER\_GO|IDG\_VS\_OBJBROWSER\_SEARCH2|  
|Output|IDM\_VS\_TOOL\_OUTPUTWINDOW|IDG\_VS\_OUTPUTWINDOW\_SELECT<br /><br /> IDG\_VS\_OUTPUTWINDOW\_GOTO<br /><br /> IDG\_VS\_OUTPUTWINDOW\_NEXTPREV<br /><br /> IDG\_VS\_OUTPUTWINDOW\_CLEAR<br /><br /> IDG\_VS\_OUTPUTWINDOW\_WORDWRAP|  
|찾기 및 바꾸기|IDM\_VS\_TOOL\_UNIFIEDFIND|IDG\_VS\_FINDTAB<br /><br /> IDG\_VS\_REPLACETAB|  
|찾기 결과 1|IDM\_VS\_TOOL\_FINDRESULTS1|IDG\_VS\_FINDRESULTS1\_GOTO<br /><br /> IDG\_VS\_FINDRESULTS1\_NEXTPREV<br /><br /> IDG\_VS\_FINDRESULTS1\_CLEAR<br /><br /> IDG\_VS\_FINDRESULTS1\_STOPFIND|  
|찾기 결과 2|IDM\_VS\_TOOL\_FINDRESULTS2|IDG\_VS\_FINDRESULTS2\_GOTO<br /><br /> IDG\_VS\_FINDRESULTS2\_NEXTPREV<br /><br /> IDG\_VS\_FINDRESULTS2\_CLEAR<br /><br /> IDG\_VS\_FINDRESULTS2\_STOPFIND|  
|Snippet|IDM\_VS\_TOOL\_SNIPPETMENUS|IDG\_VS\_SNIPPET\_REPL<br /><br /> IDG\_VS\_SNIPPET\_REF<br /><br /> IDG\_VS\_SNIPPET\_PROP|  
|책갈피|IDM\_VS\_TOOL\_BOOKMARKWIND|IDG\_VS\_BWNEWFOLDER<br /><br /> IDG\_VS\_BWNEXTBM<br /><br /> IDG\_VS\_BWNEXTBMF<br /><br /> IDG\_VS\_BWENABLE<br /><br /> IDG\_VS\_BWDELETE|  
|작업 목록|IDM\_VS\_TOOL\_TASKLIST|IDG\_VS\_TASKLIST\_PROVIDERLIST|  
|사용자 작업|IDM\_VS\_TOOL\_USERTASKS|IDG\_VS\_TASKLIST\_PROVIDERLIST<br /><br /> IDG\_VS\_USERTASKS\_EDIT|  
|오류 목록|IDM\_VS\_TOOL\_ERRORLIST|IDG\_VS\_ERRORLIST\_ERRORGROUP<br /><br /> IDG\_VS\_ERRORLIST\_WARNINGGROUP<br /><br /> IDG\_VS\_ERRORLIST\_MESSAGEGROUP|  
|호출 브라우저|IDM\_VS\_TOOL\_CALLBROWSER1.16|IDG\_VS\_TOOLBAR\_CALLBROWSER1\_ACTIONS<br /><br /> IDG\_VS\_TOOLBAR\_CALLBROWSER1\_TYPE<br /><br /> IDG\_VS\_TOOLBAR\_CALLBROWSER1\_CBSETTINGS|  
|중단점|guidVSDebugGroup:IDM\_BREAKPOINTS\_WINDOW\_TOOLBAR|IDG\_BREAKPOINTS\_WINDOW\_NEW<br /><br /> IDG\_BREAKPOINTS\_WINDOW\_DELETE<br /><br /> IDG\_BREAKPOINTS\_WINDOW\_ALL<br /><br /> IDG\_BREAKPOINTS\_WINDOW\_VIEW<br /><br /> IDG\_BREAKPOINTS\_WINDOW\_EDIT<br /><br /> IDG\_BREAKPOINTS\_WINDOW\_COLUMNS|  
|디스어셈블리|guidVSDebugGroup:IDM\_DISASM\_WINDOW\_TOOLBAR|IDG\_DISASM\_WINDOW\_TOOLBAR|  
|메모리 1\-4|guidVSDebugGroup:IDM\_MEMORY\_WINDOW\_TOOLBAR1…4|IDG\_MEMORY\_EXPRESSION1.4<br /><br /> IDG\_MEMORY\_COLUMNS1.4|  
|프로세스|guidVSDebugGroup:IDM\_ATTACHED\_PROCS\_TOOLBAR|IDG\_ATTACHED\_PROCS\_EXECCNTRL IDG\_ATTACHED\_PROCS\_STEPPING<br /><br /> IDG\_ATTACHED\_PROCS\_EXECCNTRL2<br /><br /> IDG\_ATTACHED\_PROCS\_ATTACH<br /><br /> IDG\_ATTACHED\_PROCS\_COLUMNS|  
  
## 참고 항목  
 [도구 모음에 메뉴 컨트롤러 추가](../../extensibility/adding-a-menu-controller-to-a-toolbar.md)   
 [도구 창에는 도구 모음 추가](../../extensibility/adding-a-toolbar-to-a-tool-window.md)   
 [Guid 및 Id의 Visual Studio 메뉴](../../extensibility/internals/guids-and-ids-of-visual-studio-menus.md)
---
title: "Guid 및 Id의 Visual Studio 메뉴 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "visual studio 메뉴"
  - "visual studio 그룹"
  - "ID"
  - "기존 메뉴"
  - "guid"
  - "메뉴"
ms.assetid: 84639d86-dd21-4b35-9988-6bb654162488
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# Guid 및 Id의 Visual Studio 메뉴
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 항목의 메뉴와 Visual Studio 메뉴 모음에서 그룹 GUID 및 ID 값을 열거 합니다. 이러한 값은 Visual Studio SDK의 일부로 설치 되는.vsct 파일에 정의 됩니다. 자세한 내용은 [IDE 정의 명령, 메뉴 및 그룹](../../extensibility/internals/ide-defined-commands-menus-and-groups.md)을 참조하세요.  
  
 .Vsct 파일에 정의 된 통합된 개발 환경 \(IDE\) 개체를 사용 하는 방법에 대 한 자세한 내용은 참조 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)합니다.  
  
 메뉴 및 Visual Studio 메뉴 모음에서 그룹의 GUID를 사용 하 여 `guidSHLMainMenu`합니다. 메뉴 모음 자체의 ID가 `IDM_VS_TOOL_MAINMENU`합니다.  
  
## Visual Studio 메뉴 모음에서 그룹  
 메뉴 모음에 메뉴를 추가 하려면 이러한 그룹 중 하나를 부모로 설정 합니다.  
  
|그룹화|ID|  
|---------|--------|  
|파일\/편집\/보기|IDG\_VS\_MM\_FILEEDITVIEW|  
|리팩터링|IDG\_VS\_MM\_REFACTORING:|  
|프로젝트|IDG\_VS\_MM\_PROJECT|  
|빌드|IDG\_VS\_MM\_BUILDDEBUGRUN|  
|형식\/도구|IDG\_VS\_MM\_TOOLSADDINS|  
|창\/도움말\/커뮤니티|IDG\_VS\_MM\_WINDOWHELP|  
|추가 기능|IDG\_VS\_MM\_MACROS|  
|FullScreenBar|IDG\_VS\_MM\_FULLSCREENBAR|  
  
## Visual Studio 메뉴 모음에서 메뉴  
 기존 Visual Studio 메뉴에는 그룹을 추가 하려면 다음 메뉴 중 하나를 부모로 설정 합니다. 이 목록에 하위 메뉴가 포함 되지 않습니다.  
  
|메뉴|ID|  
|--------|--------|  
|파일|IDM\_VS\_MENU\_FILE|  
|편집|IDM\_VS\_MENU\_EDIT|  
|보기|IDM\_VS\_MENU\_VIEW|  
|리팩터링|IDM\_VS\_MENU\_REFACTORING|  
|프로젝트|IDM\_VS\_MENU\_PROJECT|  
|빌드|IDM\_VS\_MENU\_BUILD|  
|서식|IDM\_VS\_MENU\_FORMAT|  
|도구|IDM\_VS\_MENU\_TOOLS|  
|창|IDM\_VS\_MENU\_WINDOW|  
|추가 기능|IDM\_VS\_MENU\_ADDINS|  
|커뮤니티|IDM\_VS\_MENU\_COMMUNITY|  
|도움말|IDM\_VS\_MENU\_HELP|  
  
## Visual Studio 메뉴에는 그룹  
 다음 목록에서는 Visual Studio 메뉴 모음에서 메뉴에서 직접 상속 하는 그룹을 나타냅니다. Visual Studio 메뉴에 명령을 추가 하는 가장 빠른 방법은 부모와 이러한 그룹 중 하나를 설정 하는 것입니다. 이 섹션에는 하위 메뉴에서 물려받은 그룹 표시 되지 않습니다.  
  
### 파일 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|새\/열기|IDG\_VS\_FILE\_FILE|  
|Add|IDG\_VS\_FILE\_ADD|  
|솔루션|IDG\_VS\_FILE\_SOLUTION|  
|기타|IDG\_VS\_FILE\_MISC|  
|저장|IDG\_VS\_FILE\_SAVE|  
|이름 바꾸기|IDG\_VS\_FILE\_RENAME|  
|브라우저|IDG\_VS\_FILE\_BROWSER|  
|인쇄|IDG\_VS\_FILE\_PRINT|  
|가장 최근에 사용|IDG\_VS\_FILE\_MRU|  
|이동|IDG\_VS\_FILE\_MOVE|  
|끝내기|IDG\_VS\_FILE\_EXIT|  
  
### 메뉴 그룹 편집  
  
|그룹화|ID|  
|---------|--------|  
|실행 취소\/다시 실행|IDG\_VS\_EDIT\_UNDOREDO|  
|잘라내기\/복사\/붙여넣기|IDG\_VS\_EDIT\_CUTCOPY|  
|선택|IDG\_VS\_EDIT\_SELECT|  
|GoTo|IDG\_VS\_EDIT\_GOTO|  
|Find|IDG\_VS\_EDIT\_FIND|  
|체크 인|IDG\_VS\_EDIT\_OBJECTS|  
|OLE 동사|IDG\_VS\_EDIT\_OLEVERBS|  
|잘 명령|IDG\_VS\_EDIT\_COMMANDWELL|  
  
### 리팩터링 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|Common|IDG\_REFACTORING\_COMMON|  
|고급|IDG\_REFACTORING\_ADVANCED|  
  
### 보기 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|폼 코드|IDG\_VS\_VIEW\_FORMCODE|  
|브라우저|IDG\_VS\_VIEW\_BROWSER|  
|뷰를 정의 합니다.|IDG\_VS\_VIEW\_DEFINEVIEWS|  
|창|IDG\_VS\_VIEW\_WINDOWS|  
|Windows를 설계 합니다.|IDG\_VS\_VIEW\_ARCH\_WINDOWS|  
|조직의 Windows|IDG\_VS\_VIEW\_ORG\_WINDOWS|  
|코드 브라우저|IDG\_VS\_VIEW\_CODEBROWSENAV\_WINDOWS|  
|Windows 개발자|IDG\_VS\_VIEW\_DEV\_WINDOWS|  
|도구 모음|IDG\_VS\_VIEW\_TOOLBARS|  
|기호|IDG\_VS\_VIEW\_SYMBOLNAVIGATE|  
|이동|IDG\_VS\_VIEW\_NAVIGATE|  
|작은 이동|IDG\_VS\_VIEW\_SMALLNAVIGATE|  
|개체 브라우저|IDG\_VS\_VIEW\_OBJBRWSR|  
|잘 명령|IDG\_VS\_VIEW\_COMMANDWELL|  
|속성 페이지|IDG\_VS\_VIEW\_PROPPAGES|  
|새로 고침|IDG\_VS\_VIEW\_REFRESH|  
  
### 프로젝트 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|기타 추가|IDG\_VS\_PROJ\_MISCADD|  
|Add|IDG\_VS\_PROJ\_ADD|  
|폴더|IDG\_VS\_PROJ\_FOLDER|  
|Unload\/다시 로드|IDG\_VS\_PROJ\_UNLOADRELOAD|  
|참조|IDG\_VS\_PROJ\_REFERENCE|  
|옵션|IDG\_VS\_PROJ\_OPTIONS|  
|설정|IDG\_VS\_PROJ\_SETTINGS|  
  
### 빌드 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|솔루션|IDG\_VS\_BUILD\_SOLUTION|  
|선택|IDG\_VS\_BUILD\_SELECTION|  
|프로필 기반 최적화|IDG\_VS\_PGO\_SELECTION|  
|기타|IDG\_VS\_BUILD\_MISC|  
|취소|IDG\_VS\_BUILD\_CANCEL|  
  
### 도구 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|명령줄|IDG\_VS\_TOOLS\_CMDLINE|  
|코드 조각|IDG\_VS\_TOOLS\_SNIPPETS|  
|개체 하위 집합|IDG\_VS\_TOOLS\_OBJSUBSET|  
|옵션|IDG\_VS\_TOOLS\_OPTIONS|  
|다른 2|IDG\_VS\_TOOLS\_OTHER2|  
|외부 도구|IDG\_VS\_TOOLS\_EXT\_TOOLS|  
|외부 사용자 지정|IDG\_VS\_TOOLS\_EXT\_CUST|  
  
### 창 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|새로 만들기|IDG\_VS\_WINDOW\_NEW|  
|도킹\/닫기|IDG\_VS\_DOCKCLOSE|  
|도킹\/숨기기|IDG\_VS\_DOCKHIDE|  
|정렬|IDG\_VS\_WINDOW\_ARRANGE|  
|탐색|IDG\_VS\_WINDOW\_NAVIGATION|  
|목록|IDG\_VS\_WINDOW\_LIST|  
  
### 도움말 메뉴 그룹  
  
|그룹화|ID|  
|---------|--------|  
|샘플|IDG\_VS\_HELP\_SAMPLES|  
|지원|IDG\_VS\_HELP\_SUPPORT|  
|정보|IDG\_VS\_HELP\_ABOUT|  
  
## Visual Studio 메뉴의 하위 메뉴  
 다음 계층에서는 Visual Studio 메뉴 모음에서 메뉴와 연결 된 하위 메뉴를 보여 줍니다. 그룹에만 부모 메뉴를 가질 수 있으므로 모든 하위 메뉴 해야에서 물려 그룹 메뉴에서 대신 메뉴에서 직접. 메뉴, 그룹 및 하위 메뉴의 관계에 대 한 자세한 내용은 참조 [하위 메뉴에 추가](../../extensibility/adding-a-submenu-to-a-menu.md)합니다.  
  
> [!NOTE]
>  Visual Studio 메뉴 모음에서 메뉴 이름이 표시 되지 않습니다 별도로이 계층에서 다음과 같이 IDE에서 그룹에 대 한 명명 규칙에서 유추할 수 있는 때문에: IDG\_VS\_*메뉴 이름*\_*그룹 이름*합니다.  
  
|부모 그룹|하위 메뉴|자식 그룹|  
|-----------|-----------|-----------|  
|IDG\_VS\_FILE\_FILE|IDM\_VS\_CSCD\_NEW|IDG\_VS\_FILE\_NEW\_CASCADE|  
||IDM\_VS\_CSCD\_OPEN|IDG\_VS\_FILE\_OPENP\_CASCADE|  
|||IDG\_VS\_FILE\_OPENF\_CASCADE|  
|IDG\_VS\_FILE\_ADD|IDM\_VS\_CSCD\_ADD|IDG\_VS\_FILE\_ADD\_PROJECT\_NEW|  
|||IDG\_VS\_FILE\_ADD\_PROJECT\_EXI|  
|IDG\_VS\_FILE\_MRU|IDM\_VS\_CSCD\_FILEMRU|IDG\_VS\_FILE\_FMRU\_CASCADE|  
||IDM\_VS\_CSCD\_PROJMRU|IDG\_VS\_FILE\_PMRU\_CASCADE|  
|IDG\_VS\_FILE\_MOVE|IDM\_VS\_CSCD\_MOVETOPRJ|IDG\_VS\_FILE\_MOVE\_CASCADE|  
|||IDG\_VS\_FILE\_MOVE\_PICKER|  
|IDG\_VS\_VIEW\_DEV\_WINDOWS|IDM\_VS\_CSCD\_FINDRESULTS|IDG\_VS\_WNDO\_FINDRESULTS|  
||IDM\_VS\_CSCD\_WINDOWS|IDG\_VS\_VIEW\_CALLBROWSER|  
|||IDG\_VS\_WNDO\_OTRWNDWS1... 6|  
|||IDG\_VS\_WNDO\_WINDOWS2|  
|IDG\_VS\_VIEW\_TOOLBARS|IDM\_VS\_CSCD\_COMMANDBARS||  
|IDG\_VS\_EDIT\_GOTO|IDM\_VS\_EDITOR\_FIND\_MENU||  
|IDG\_VS\_EDIT\_OBJECTS|IDM\_VS\_CSCD\_MNUDES|IDG\_VS\_MNUDES\_INSERT|  
|||IDG\_VS\_MNUDES\_EDITNAMES|  
||IDM\_VS\_CSCD\_OLEVERBS|IDG\_VS\_EDIT\_OLEVERBS|  
|IDG\_VS\_BUILD\_SELECTION|IDM\_VS\_CSCD\_BUILD|IDG\_VS\_BUILD\_CASCADE|  
|||IDG\_VS\_BUILD\_PROJPICKER|  
||IDM\_VS\_CSCD\_REBUILD|IDG\_VS\_REBUILD\_CASCADE|  
|||IDG\_VS\_REBUILD\_PROJPICKER|  
||IDM\_VS\_CSCD\_PROJONLY|IDG\_VS\_PROJONLY\_CASCADE|  
||IDM\_VS\_CSCD\_CLEAN|IDG\_VS\_CLEAN\_CASCADE|  
|||IDG\_VS\_CLEAN\_PROJPICKER|  
||IDM\_VS\_CSCD\_DEPLOY|IDG\_VS\_DEPLOY\_CASCADE|  
|||IDG\_VS\_DEPLOY\_PROJPICKER|  
|IDG\_VS\_PGO\_SELECTION|IDM\_VS\_CSCD\_PGO\_BUILD|IDG\_VS\_PGO\_BUILD\_CASCADE\_BUILD|  
|||IDG\_VS\_PGO\_BUILD\_CASCADE\_RUN|  
  
## 참고 항목  
 [Guid 및 Visual Studio 도구 모음의 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-toolbars.md)   
 [Guid 및 Visual Studio 명령 Id](../../extensibility/internals/guids-and-ids-of-visual-studio-commands.md)   
 [Visual Studio 명령 테이블 \(. Vsct\) 파일](../../extensibility/internals/visual-studio-command-table-dot-vsct-files.md)
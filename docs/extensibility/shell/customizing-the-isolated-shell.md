---
title: "격리 셸 사용자 지정 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: Visual Studio shell, isolated mode
ms.assetid: e0b7c3ae-210f-4f48-ac49-6a59e6034f5f
caps.latest.revision: "15"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 98cf51c539f34b3ad0a843a055603bd5480d2b24
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="customizing-the-isolated-shell"></a>격리 셸 사용자 지정
Visual Studio 사용자 인터페이스의 다양 한 측면을 변경 하 고 명령 및 특수화 된 응용 프로그램에 포함 된 기능을 제한 하 여 Visual Studio 격리 셸 응용 프로그램을 사용자 지정할 수 있습니다.  
  
## <a name="using-the-applicationpkgdef-file"></a>Application.pkgdef 파일을 사용 하 여  
 격리 셸 서식 파일 솔루션에는 *SolutionName*합니다. 다음과 같은 기능을 수정할 수 있는 Application.pkgdef 파일:  
  
##### <a name="the-application-title"></a>응용 프로그램 제목  
 이름에 "AppName" 행의 값을 변경 하 여 응용 프로그램의 제목 표시줄에 표시 되는 응용 프로그램 제목을 사용자 지정할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
 현재 로드 된 프로젝트를 표시 하는 응용 프로그램 제목 하지 않으려면 "ShowHierarchyRootInTitle"에서 행의 값을 변경할는 *SolutionName*합니다. Dword: 00000001 dword: 00000000 파일을 Application.pkgdef입니다.  
  
##### <a name="the-application-icon"></a>응용 프로그램 아이콘  
 응용 프로그램 아이콘 응용 프로그램 제목 표시줄에 응용 프로그램 이름으로 표시 되는 아이콘을 사용자 지정할 수 있습니다. 다른 아이콘 아이콘 디렉터리로 복사 합니다. **솔루션 탐색기**, 리소스 파일 폴더에 아이콘을 추가 합니다. VSShellStub.rc 파일 열고 IDI_STUBPROGRAM의 값을 새 아이콘의 이름으로 바꿉니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
##### <a name="the-command-line-logo"></a>명령줄 로고  
 응용 프로그램에서 "CommandLineLogo" 행의 값을 변경 하 여 명령줄에서 시작 될 때 표시 되는 텍스트는 명령줄 로고를 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### <a name="the-name-of-the-user-files-subfolder"></a>사용자 파일 하위 폴더의 이름  
 응용 프로그램에서 "UserFilesSubFolderName" 행의 값을 변경 하 여 사용자 파일에 유지 하는 폴더의 이름을 변경할 수 있습니다 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-title-of-the-solution-tree-node-in-the-new-project-dialog"></a>새 프로젝트 대화 상자에서 솔루션 트리 노드 제목  
 새 프로젝트 대화 상자에서 솔루션 노드 제목에서 "NewProjDlgSlnTreeNodeTitle" 행의 값을 변경 하 여 사용자 지정할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-installed-templates-header-in-the-new-project-dialog"></a>새 프로젝트 대화 상자에 설치 된 템플릿 헤더  
 새 프로젝트 대화 상자에 설치 되어 있는 템플릿 헤더에서 "NewProjDlgInstalledTemplatesHdr" 행의 값을 변경 하 여 변경할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="whether-or-not-to-hide-miscellaneous-files-by-default"></a>기본적으로 기타 파일 숨기기 여부  
 "HideMiscellaneousFilesByDefault" 행의 값을 변경 하 여 기본적으로 기타 파일 숨기기 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 기타 파일을 숨기려면 값 설정 `dword:00000001`, 파일을 표시 하려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### <a name="whether-or-not-to-disable-the-output-window"></a>출력 창 사용 하지 않도록 설정 여부  
 응용 프로그램의 출력 창에서 "DisableOutputWindow" 행의 값을 변경 하 여 사용 하지 않도록 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 출력 창을 해제 하려면 값을 설정 `dword:00000001`, 출력 창을 표시 하려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### <a name="whether-or-not-to-allow-dropped-files-on-the-main-window"></a>주 창에서 삭제 된 파일 허용 여부  
 응용 프로그램의 주 창에서 삭제 된 파일에서 "AllowsDroppedFilesOnMainWindow" 행의 값을 변경 하 여 허용 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 삭제 된 파일을 허용 하려면 값을 설정 `dword:00000001`, 삭제 된 파일을 허용 하지 않을 값을 설정 하 고 `dword:00000000`합니다.  
  
##### <a name="the-default-search-page"></a>기본 검색 페이지  
 가 열리면 웹 브라우저 창에서 "DefaultSearchPage" 행의 값을 변경 하 여 표시 되는 페이지는 웹 브라우저 페이지를 사용자 지정할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-default-home-page"></a>기본 홈 페이지  
 홈 페이지에서 "DefaultHomePage" 행의 값을 변경 하 여 사용자 지정할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### <a name="whether-or-not-to-hide-the-solution-concept"></a>솔루션 개념 숨길 것인지 여부  
 응용 프로그램에서 솔루션에 "HideSolutionConcept" 행의 값을 변경 하 여 숨길 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 값을 설정 하는 솔루션을 숨기려면 `dword:00000001`, 솔루션을 표시 하려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### <a name="the-default-debug-engine"></a>기본 디버그 엔진  
 응용 프로그램에서 "DefaultDebugEngine" 행의 값을 변경 하 여 사용 하 여 디버그 엔진을 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일 디버그 엔진의 GUID입니다.  
  
##### <a name="the-file-extension-of-the-user-options-file"></a>사용자 옵션 파일의 파일 확장명  
 응용 프로그램에서 "UserOptsFileExt" 행의 값을 변경 하 여 사용자 파일에 유지 하는 폴더의 이름을 변경할 수 있습니다 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-solution-file-extension"></a>솔루션 파일 확장명  
 "SolutionFileExt" 행의 값을 변경 하 여 솔루션 파일에 대해 사용 되는 확장을 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-default-user-files-folder-root"></a>기본 사용자 파일 폴더 루트  
 "UserFilesSubFolderName" 행의 값을 변경 하 여 응용 프로그램에 대 한 사용자 파일의 루트 폴더의 이름을 변경할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-solution-file-creator-identifier"></a>솔루션 파일 작성자 식별자  
 "SolutionFileCreatorIdentifier" 행의 값을 변경 하 여 솔루션 파일에 대해 사용 되는 식별자를 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-default-projects-location"></a>기본 프로젝트 위치  
 "DefaultProjectsLocation" 행의 값을 변경 하 여 기본 프로젝트 위치 이름을 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="the-application-localization-package"></a>응용 프로그램 지역화 패키지  
 "AppLocalizationPackage" 행의 값을 변경 하 여 응용 프로그램에 사용 되는 지역화 패키지를 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### <a name="whether-or-not-to-show-the-hierarchy-root-in-the-title"></a>계층 루트 제목에 표시할 것인지 여부  
 "ShowHierarchyRootInTitle" 행의 값을 변경 하 여 계층 루트 응용 프로그램의 제목 표시줄에 표시할 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 계층 루트를 표시 하려면 값을 설정 `dword:00000001`, 계층 루트를 숨기려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### <a name="specifying-a-start-page"></a>시작 페이지를 지정합니다.  
 사용자 지정 응용 프로그램에 대 한 시작 페이지를 지정 하는 *SolutionName*합니다. Application.pkgdef 파일 "DisableStartPage" 값을 설정 `dword:00000000`, 아래에서 `[$RootKey$\StartPage\Default]` .xaml 파일의 위치를 URI를 설정 합니다.  
  
```  
DisableStartPage=dword:00000000  
[$RootKey$\StartPage\Default]  
"Uri"="$RootFolder$\<name of XAML file>"  
```  
  
 Applicationcommands.vsct 파일에 *SolutionName*UI 프로젝트, 주석 "No_ShellPkg_startPageCommand" 항목으로 처리 합니다.  
  
```  
<!--<Define name="No_ShellPkg_StartPageCommand"/>-->  
```  
  
 에 필요한 모든 그래픽 파일 및.xaml 파일을 추가 해야는 *SolutionName* 프로젝트. 이러한 파일에 복사 실제로 해야는 *SolutionName* 프로젝트 디렉터리에 다른 디렉터리에서 추가 되지 않습니다.  
  
 모든 파일에서 설정 된 **항목 형식** 속성을 **격리 셸 파일** 에 복사할 파일에 대 한 순서 대로 *$RootFolder$* 디렉터리. (설정 하는 **항목 형식** 속성 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 이 속성에서 확인할 수 **구성 속성**, **일반**.)  
  
 시작 페이지 사용자 지정에 대 한 자세한 내용은 참조 하십시오. [시작 페이지 사용자 지정](../../ide/customizing-the-start-page-for-visual-studio.md)합니다.  
  
## <a name="using-other-elements-of-the-isolated-shell"></a>격리 셸의 다른 요소를 사용 하 여  
 다른 파일 및 응용 프로그램에 대 한 격리 셸 솔루션 템플릿에 포함 된 프로젝트를 사용할 수 있습니다.  
  
##### <a name="enabledisable-visual-studio-packages"></a>Visual Studio 패키지 사용/사용 안 함  
 *SolutionName*.pkgundef 파일을 사용 하면 특정 패키지를 제외 하 여 특정 종류의 Visual Studio 기능을 해제할 수 있습니다. 예를 들어 다음 줄:  
  
```  
[$RootKey$\Projects\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}\AddItemTemplates\TemplateDirs\{39c9c826-8ef8-4079-8c95-428f5b1c323f}]  
```  
  
 기타 파일 프로젝트에 표시 되는 프로젝트 템플릿 집합에서 제거 된 **새 프로젝트** 대화 상자. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
##### <a name="enabledisable-menu-commands"></a>설정/해제 메뉴 명령  
 *SolutionName*UI.vsct 파일에 격리 셸 사용할 수 있는 모든 메뉴 명령 주석 목록이 포함 됩니다. 지정된 된 명령을 사용 하지 않으려면 해당 행을 주석 처리 제거 합니다. 예를 들어 창/분할 메모를 해제 하려면 주석 처리 제거는 `<Define name="No_SplitCommand"/>` 행입니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
##### <a name="the-bitmap-used-on-the-splash-screen"></a>시작 화면에 사용 되는 비트맵  
 "SplashScreenBitmap" 행의 값을 변경 하 여 응용 프로그램이 시작 될 때 표시 되는 창 시작 화면에서 사용 되는 비트맵을 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.  
  
##### <a name="the-helpabout-window"></a>도움말/정보 창  
 격리 셸 템플릿에서 도움말을 사용자 지정 하는 데 사용할 수는 별도 프로젝트/응용 프로그램에 대 한 상자에 대 한 합니다. 자세한 내용은 참조 하십시오. [연습: 기본 격리 셸 응용 프로그램 만들기](walkthrough-creating-a-basic-isolated-shell-application.md)합니다.
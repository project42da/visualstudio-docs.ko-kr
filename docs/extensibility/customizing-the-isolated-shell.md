---
title: "격리 된 셸 사용자 지정 | Microsoft Docs"
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
  - "Visual Studio shell 격리 모드"
ms.assetid: e0b7c3ae-210f-4f48-ac49-6a59e6034f5f
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# 격리 된 셸 사용자 지정
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 사용자 인터페이스의 다양 한 측면을 변경 하 고 명령 및 특수 한 응용 프로그램에 포함 된 기능을 제한 하 여 Visual Studio isolated shell 응용 프로그램을 사용자 지정할 수 있습니다.  
  
## Application.pkgdef 파일을 사용 하 여  
 격리 된 셸 서식 파일 솔루션에는 *SolutionName*합니다. 다음과 같은 기능을 수정할 수 있도록 Application.pkgdef 파일:  
  
##### 응용 프로그램 제목  
 이름에서 "응용 프로그램 이름" 행의 값을 변경 하 여 응용 프로그램의 제목 표시줄에 표시 되는 응용 프로그램 제목 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)을 참조하십시오.  
  
 현재 로드 된 프로젝트를 표시 하는 응용 프로그램 제목, 원하지 않는 변경에서 "ShowHierarchyRootInTitle" 행의 값은 *SolutionName*합니다. Application.pkgdef 파일은 dword: 00000001 dword:00000000입니다.  
  
##### 응용 프로그램 아이콘  
 응용 프로그램 제목 표시줄에 응용 프로그램 이름으로 표시 되는 아이콘은 응용 프로그램 아이콘을 사용자 지정할 수 있습니다. 다른 아이콘 아이콘 디렉터리에 복사 합니다.**솔루션 탐색기**, 리소스 파일 폴더에 아이콘을 추가 합니다. 그런 다음 VSShellStub.rc 파일을 열고 새 아이콘의 이름으로 IDI\_STUBPROGRAM의 값을 대체 합니다. 자세한 내용은 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)을 참조하십시오.  
  
##### 명령줄 로고  
 응용 프로그램에서 "CommandLineLogo" 행의 값을 변경 하 여 명령줄에서 시작 될 때 나타나는 텍스트는 명령줄 로고를 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 다음을 참조 하십시오. [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### 사용자 파일 하위 폴더의 이름  
 "UserFilesSubFolderName" 행의 값을 변경 하 여 사용자 파일에 대 한 유지 관리 응용 프로그램 폴더의 이름을 변경할 수 있습니다 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 새 프로젝트 대화 상자에서 솔루션 트리 노드의 제목  
 새 프로젝트 대화 상자에서 솔루션 노드의 제목에 "NewProjDlgSlnTreeNodeTitle" 행의 값을 변경 하 여 사용자 지정할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 새 프로젝트 대화 상자에서 설치 된 템플릿 헤더  
 "NewProjDlgInstalledTemplatesHdr" 행의 값을 변경 하 여 새 프로젝트 대화 상자에서 설치 된 템플릿 헤더를 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 기본적으로 기타 파일을 숨길 것인지 여부  
 "HideMiscellaneousFilesByDefault" 행의 값을 변경 하 여 기본적으로 기타 파일을 숨길 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 기타 파일을 숨기려면 값 설정 `dword:00000001`, 파일을 표시 하려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### 출력 창 사용 하지 않도록 설정할 것인지 여부  
 응용 프로그램의 출력 창에 "DisableOutputWindow" 행의 값을 변경 하 여 사용 하지 않도록 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 출력 창을 사용 하지 않으려면 값을 설정 `dword:00000001`, 출력 창에 표시 하려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### 주 창에서 끌어 놓은 파일 허용 여부  
 응용 프로그램의 주 창에 끌어 놓은 파일에서 "AllowsDroppedFilesOnMainWindow" 행의 값을 변경 하 여 허용 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 끌어 놓은 파일을 허용 하려면 값을 설정 `dword:00000001`, 끌어 놓은 파일을 허용 하지 않으려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### 기본 검색 페이지  
 가 열리면 웹 브라우저 창에서 "DefaultSearchPage" 행의 값을 변경 하 여 표시 되는 페이지는 웹 브라우저 페이지를 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 기본 홈 페이지  
 "DefaultHomePage" 행의 값을 변경 하 여 홈 페이지를 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 다음을 참조 하십시오. [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
##### 솔루션 개념 숨길 것인지 여부  
 "HideSolutionConcept" 행의 값을 변경 하 여 응용 프로그램에서 솔루션을 숨길 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 값을 설정 하는 솔루션을 숨기려면 `dword:00000001`, 솔루션을 표시 하려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### 기본 디버그 엔진  
 응용 프로그램에서 "DefaultDebugEngine" 행의 값을 변경 하 여 사용 하는 디버그 엔진을 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일 디버그 엔진의 GUID입니다.  
  
##### 사용자 옵션 파일의 파일 확장명  
 "UserOptsFileExt" 행의 값을 변경 하 여 사용자 파일에 대 한 유지 관리 응용 프로그램 폴더의 이름을 변경할 수 있습니다 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 솔루션 파일 확장명  
 "SolutionFileExt" 행의 값을 변경 하 여 솔루션 파일에 대해 사용 되는 확장을 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 기본 사용자 파일의 폴더 루트  
 "UserFilesSubFolderName" 행의 값을 변경 하 여 응용 프로그램에 대 한 사용자 파일의 루트 폴더의 이름을 변경할 수 있습니다는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 솔루션 파일 작성자 식별자  
 "SolutionFileCreatorIdentifier" 행의 값을 변경 하 여 솔루션 파일에 대해 사용 되는 식별자를 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 기본 프로젝트 위치  
 "DefaultProjectsLocation" 행의 값을 변경 하 여 기본 프로젝트 위치 이름을 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 응용 프로그램 지역화 패키지  
 "AppLocalizationPackage" 행의 값을 변경 하 여 응용 프로그램에 사용 되는 지역화 패키지를 변경할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다.  
  
##### 제목에 계층 구조의 루트를 표시 하는지 여부  
 "ShowHierarchyRootInTitle" 행의 값을 변경 하 여 계층 구조의 루트 응용 프로그램에서 제목 표시줄에 표시할 것인지 여부를 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 계층 구조의 루트를 표시 하려면 값을 설정 `dword:00000001`, 계층 구조의 루트를 숨기려면 값을 설정 하 고 `dword:00000000`합니다.  
  
##### 시작 페이지를 지정합니다.  
 사용자 지정 응용 프로그램의 시작 페이지를 지정 하는 *SolutionName*합니다. "DisableStartPage" 값을 설정 하는 Application.pkgdef 파일 `dword:00000000`, 아래에서 `[$RootKey$\StartPage\Default]` .xaml 파일의 위치 URI를 설정 합니다.  
  
```  
DisableStartPage=dword:00000000  
[$RootKey$\StartPage\Default]  
"Uri"="$RootFolder$\<name of XAML file>"  
```  
  
 Applicationcommands.vsct 파일에는 *SolutionName*UI 프로젝트, 주석 "No\_ShellPkg\_startPageCommand" 항목으로 처리 합니다.  
  
```  
<!--<Define name="No_ShellPkg_StartPageCommand"/>-->  
```  
  
 .Xaml 파일 및에 필요한 모든 그래픽 파일을 추가 해야는 *SolutionName* 프로젝트입니다. 이러한 파일에 실제로 복사 해야는 *SolutionName* 프로젝트 디렉터리에 몇 가지 다른 디렉터리에서 추가 되지 않습니다.  
  
 모든 파일에서 설정의 **항목 형식** 속성을 **격리 된 셸 파일** 위해 파일을 복사할 수는 *$RootFolder$* 디렉터리입니다. \(설정 하는 **항목 형식** 속성 파일을 마우스 오른쪽 단추로 클릭 하 고 선택 **속성**합니다. 이 속성 목록은 **구성 속성**, **일반**.\)  
  
 시작 페이지 사용자 지정에 대 한 자세한 내용은 참조 하십시오. [시작 페이지 사용자 지정](../ide/customizing-the-start-page-for-visual-studio.md)합니다.  
  
## 격리 된 셸의 다른 요소를 사용 하 여  
 다른 파일 및 응용 프로그램은 격리 된 셸 솔루션 서식 파일에 포함 된 프로젝트를 사용할 수 있습니다.  
  
##### Visual Studio 패키지 사용\/사용 안 함  
 *SolutionName*.pkgundef 파일을 사용 하면 특정 패키지를 제외 하 여 특정 종류의 Visual Studio 기능을 해제할 수 있습니다. 예를 들어, 다음 줄:  
  
```  
[$RootKey$\Projects\{A2FE74E1-B743-11d0-AE1A-00A0C90FFFC3}\AddItemTemplates\TemplateDirs\{39c9c826-8ef8-4079-8c95-428f5b1c323f}]  
```  
  
 기타 파일 프로젝트에 표시 되는 프로젝트 템플릿 집합에서 제거 된 **새 프로젝트** 대화 합니다. 자세한 내용은 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)을 참조하십시오.  
  
##### 설정\/해제 메뉴 명령  
 *SolutionName*UI.vsct 파일에는 격리 된 셸을 사용할 수 있는 모든 메뉴 명령의 주석 목록이 포함 됩니다. 지정된 된 명령을 사용 하지 않으려면 해당 행의 주석 처리를 제거 합니다. 예를 들어 창\/분할 메모를 사용 하지 않으려면 주석 처리를 제거는 `<Define name="No_SplitCommand"/>` 행입니다. 자세한 내용은 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)을 참조하십시오.  
  
##### 시작 화면에 사용 된 비트맵  
 창인에서 "SplashScreenBitmap" 행의 값을 변경 하 여 응용 프로그램이 시작 될 때 표시 되는 시작 화면에서 사용 되는 비트맵을 사용자 지정할 수는 *SolutionName*합니다. Application.pkgdef 파일입니다. 자세한 내용은 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)을 참조하십시오.  
  
##### 도움말\/창에 대 한  
 격리 된 셸 템플릿에서 도움말을 사용자 지정 하는 데 별도 프로젝트\/응용 프로그램에 대 한 상자에 대 한 합니다. 자세한 내용은 [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)을 참조하십시오.
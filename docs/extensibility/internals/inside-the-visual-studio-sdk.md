---
title: "Visual studio SDK | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "로드맵, Visual Studio SDK 통합"
  - "Visual Studio 통합 SDK 로드맵"
  - "Visual Studio SDK를 통합 로드맵"
ms.assetid: 9118eaa4-0453-4dc5-9e16-c7062d254869
caps.latest.revision: 30
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 30
---
# Visual studio SDK
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 섹션에서는 Visual Studio 아키텍처, 구성 요소, 서비스, 스키마, 유틸리티 등을 포함 하 여 Visual Studio 확장에 대 한 자세한 정보를 제공 합니다.  
  
## 확장 아키텍처  
 다음 그림에서는 Visual Studio 확장성 아키텍처를 보여 줍니다. Vspackage 서비스로 IDE에서 공유 되는 응용 프로그램 기능을 제공 합니다. 표준 IDE 역시 광범위 한 서비스와 같은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, 을 IDE 창 작업 기능에 대 한 액세스를 제공 합니다.  
  
 ![환경 아키텍처 그래픽](../../extensibility/internals/media/environment.png "environment")  
Visual Studio 아키텍처의 일반화 된 보기  
  
## Vspackage  
 Vspackage를 구성 하 고 UI 요소, 서비스, 프로젝트, 편집기 및 디자이너와 Visual Studio를 확장 하는 소프트웨어 모듈 됩니다. Vspackage은 Visual Studio의 중앙 아키텍처 단위입니다. 자세한 내용은 [Vspackage](../../extensibility/internals/vspackages.md)을 참조하세요.  
  
## Visual Studio Shell  
 Visual Studio 셸은 기본 기능을 제공 하 고 해당 구성 요소 Vspackage 및 MEF 확장 간에 간 통신을 지원 합니다. 자세한 내용은 [Visual Studio Shell](../../extensibility/internals/visual-studio-shell.md)을 참조하십시오.  
  
## 사용자 환경 지침  
 Visual Studio에 대 한 새로운 기능을 디자인 하려는 경우에 디자인 및 유용성 팁에 대 한 이러한 지침 살펴보기 수행 해야: [Visual Studio 사용자 환경 지침](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
## 명령  
 명령에는 문서를 인쇄, 보기, 새로 고침 또는 새 파일을 만드는 등의 작업을 수행 하는 함수입니다.  
  
 Visual Studio를 확장 하면 명령을 만들고 Visual Studio shell에 등록할 수 있습니다. 이러한 명령은 모양을 IDE에 예를 들어 메뉴 또는 도구 모음에서 지정할 수 있습니다. 사용자 지정 명령에 표시 되는 일반적으로 **도구** 메뉴 및 도구 창을 표시 하기 위한 명령에 나타나는 **다른 창** 의 하위 메뉴는 **보기** 메뉴.  
  
 명령을 만들면 사용자도 만들어야 이벤트 처리기에 대 한 합니다. 이벤트 처리기 명령을 표시 또는 활성화, 해당 텍스트를 수정할 수 있습니다 및 활성화 될 때 명령이 적절히 응답 하는지 보장 시기를 결정 합니다. IDE를 사용 하 여 명령 처리 대부분의 경우에는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. Visual Studio의 명령은 로컬 선택을 기반으로 하 고 전역 선택을 기반으로 하는 가장 바깥쪽 컨텍스트를 진행 하는 가장 안쪽의 명령 컨텍스트를부터 처리 됩니다. 주 메뉴에 추가 된 주석은 스크립팅을 위해 바로 사용할 수 있습니다.  
  
 자세한 내용은 [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)을 참조하세요.  
  
## 메뉴 및 도구 모음  
 메뉴 및 도구 모음에는 사용자의 명령을 호출 하는 방법을 제공 합니다. 메뉴는 일반적으로 도구 창 위쪽에서 개별 텍스트 항목으로 표시 되는 명령의 행 이나 열 됩니다. 하위 메뉴는 작은 화살표를 포함 하는 명령이 클릭할 때 표시 되는 보조 메뉴가 있습니다. 상황에 맞는 메뉴에는 특정 UI 요소를 클릭할 때 표시 됩니다. 몇 가지 일반적인 메뉴 이름은 **파일**, **편집**, **보기**, 및 **창**합니다. 자세한 내용은 [확장 메뉴 및 명령](../../extensibility/extending-menus-and-commands.md)을 참조하십시오.  
  
 도구 모음 단추 및 콤보 상자, 목록 상자, 텍스트 상자 등의 다른 컨트롤의 행 이나 열 됩니다. 도구 모음 단추에 대 한 폴더 아이콘 같은 아이콘 이미지를 하는 일반적으로 **파일 열기** 명령 또는 프린터에 대 한 한 **인쇄** 명령입니다. 모든 도구 모음 요소가 명령과 사용 하 여 연결 합니다. 도구 모음 단추를 클릭 하면 해당 관련 된 명령이 실행 됩니다. 드롭다운 목록 컨트롤의 경우 드롭다운 목록의 각 항목에에서는 다른 명령에 연관 됩니다. Splitter 컨트롤을 같은 일부 도구 모음 컨트롤은 모두 사전과 하이브리드입니다. 컨트롤의 한 쪽은 도구 모음 단추가 고 다른 측면은 몇 가지 명령을 클릭할 때 표시 하는 아래쪽 화살표를 합니다.  
  
## 도구 창  
 도구 창 정보를 표시 하는 IDE에서 사용 됩니다.**도구 상자**, **솔루션 탐색기**, **속성** 창 및 **웹 브라우저** 도구 창에 속합니다.  
  
 일반적으로 도구 창을 사용자 작용할 수 있는 다양 한 컨트롤을 제공 합니다. 예를 들어,는 **속성** 창에는 사용자가 특정 목적으로 사용 하는 개체의 속성을 설정할 수 있습니다.**속성** 창은 이런이 의미에서 특수 한 이지만 또한 일반 해 주는 여러 가지 상황에서 사용할 수 있습니다. 마찬가지로,는 **출력** 창이 Visual Studio의 여러 하위 시스템 출력 Visual Studio 사용자에 게 제공 하는 데 사용할 수 있지만 일반 텍스트 기반 출력을 제공 하기 때문에 전문화 될 합니다.  
  
 다음 그림의 여러 도구 창이 포함 된 Visual Studio를 고려해 야 합니다.  
  
 ![스크린 샷](../../extensibility/internals/media/t1gui.png "T1gui")  
  
 도구 창 중 일부는 솔루션 탐색기 도구 창을 표시 하 고 다른 도구 창을 숨겨지지만 탭을 클릭 하 여 사용할 수 있도록 하는 단일 창에 함께 도킹 됩니다. 그림에는 나와 다른 두 개의 도구 창에는 **오류 목록** 및 **출력** 단일 창에 함께 도킹 창.  
  
 여러 편집기 창에 표시 되는 주 문서 창을도 표시 됩니다. 도구 창에는 일반적으로 인스턴스를 하나만 필요는 없지만 \(예를 들어 하나만 열 수 있습니다 **솔루션 탐색기**\), 편집기 창에는 모두를 동일한 창에 도킹 되어 있지만 별도 문서를 편집 하는 데 사용 되는 각각의 여러 인스턴스를 가질 수 있습니다. 그림에서는 두 편집기 창, 한 양식 디자이너 창 및 시작 페이지를 표시 하는 브라우저 창이 있는 문서 창을 보여 줍니다. 문서 창에 있는 모든 창을 탭을 클릭 하 여 사용할 수 있지만 EditorPane.cs 파일을 포함 하는 편집기 창을 표시 되 고 활성화 합니다.  
  
 Visual Studio를 확장할 때 확장으로 Visual Studio 사용자가 windows 상호 작용 하는 도구를 만들 수 있습니다. Visual Studio 사용자가 문서를 편집할 수 있도록 사용자 고유의 편집기를 만들 수 있습니다. 도구 창과 편집기는 Visual Studio에 통합 될 예정, 때문에 도킹 또는 탭에서 웹 페이지가 제대로 표시를 프로그래밍할 필요가 없습니다. Visual Studio에서 등록 된 올바르게 될 때 도구 창과 문서 창 Visual Studio에서의 일반적인 기능 자동으로 생성 됩니다. 자세한 내용은 [확장 및 도구 창을 사용자 지정](../../extensibility/extending-and-customizing-tool-windows.md)을 참조하십시오.  
  
## 문서 창  
 문서 창에는 다중 문서 인터페이스 \(MDI\) 창의 자식 프레임된 창이입니다. 문서 창은 텍스트 편집기, 폼 편집기 \(라고도 디자이너\) 또는 편집 컨트롤을 호스트 하 일반적으로 사용 되지만 다른 기능 종류를 호스팅할 수도 있습니다.**새 파일** 대화 상자에 문서 창은 Visual Studio에서 제공 하는 예가 포함 되어 있습니다.  
  
 대부분의 편집기는 프로그래밍 언어 또는 HTML 페이지, 프레임, c \+ \+ 파일, 헤더 파일 등의 파일 형식에만 적용 됩니다. 템플릿을 선택 하 고 **새 파일** 대화 상자에서 사용자를 동적으로 만듭니다 문서 창에서 템플릿과 연결 된 파일 형식에 대 한 편집기에 대 한 합니다. 사용자가 기존 파일을 열 때 문서 창이 만들어집니다.  
  
 문서 창은 서 MDI 클라이언트 영역으로 제한 됩니다. 바탕 화면에서 각 문서 창에는 탭 및 탭 순서 MDI 영역에 열려 있을 수 있는 다른 창에 연결 됩니다. 여러 개의 가로 또는 세로 탭 그룹을 MDI 영역을 분할 하는 옵션을 포함 하는 바로 가기 메뉴를 표시 문서 창의 탭을 마우스 오른쪽 단추로 클릭 합니다. MDI 영역을 분할 여러 파일을을 동시에 볼 수 있습니다. 자세한 내용은 [문서 창](../../extensibility/internals/document-windows.md)을 참조하십시오.  
  
## 편집기  
 Visual Studio 편집기를 사용 하면 사용자 지정 및 관리 되는 확장성 프레임 워크 \(MEF\)를 사용 하 여 콘텐츠 유형에 사용할 수 있습니다. 대부분의 경우에서 \(예를 들어 메뉴 명령 또는 바로 가기 키\) 셸에서 기능을 포함 하려는 경우 MEF 확장을 VSPackage와 결합할 수 있습니다 있지만 편집기를 확장 하는 VSPackage를 만들 필요가 됩니다.  
  
 또한 디자이너를 사용 하려는 경우 또는 읽기 \/ 쓰기 데이터베이스를 하려는 경우 예를 들어 사용자 지정 편집기를 만들 수 있습니다. 메모장 이나 Microsoft 워드 패드와 같은 외부 편집기를 사용할 수 있습니다. 자세한 내용은 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)을 참조하십시오.  
  
## 언어 서비스  
 새로운 프로그래밍 키워드 또는 심지어 새로운 프로그래밍 언어를 지원 하기 위해 Visual Studio 편집기를 사용 하도록 하려는 경우 언어 서비스를 만듭니다. 각 언어 서비스는 완벽 하 게, 부분적으로 또는 전혀 특정 편집기 기능을 구현할 수 있습니다. 구성 방법에 따라 언어 서비스 구문 강조, 중괄호 일치, IntelliSense 지원 및 편집기에서 다른 기능을 제공할 수 있습니다.  
  
 언어 서비스의 핵심은 파서 및 스캐너입니다. 스캐너 \(또는 렉서\)는 소스 파일을 토큰 이라고 하는 요소로 나누고 파서 토큰 간의 관계를 설정 합니다. 언어 서비스를 만들 때 Visual Studio는 토큰 및 언어의 문법에 이해할 수 있도록 파서와 스캐너 구현 해야 합니다. 관리 되거나 관리 되지 않는 언어 서비스를 만들 수 있습니다. 자세한 내용은 [레거시 언어 서비스 확장](../../extensibility/internals/legacy-language-service-extensibility.md)을 참조하십시오.  
  
## 프로젝트  
 Visual Studio에서 프로젝트는 개발자가 구성 하 고 소스 코드 및 기타 리소스를 작성 하는 데 사용할 컨테이너를 사용 합니다. 구성, 빌드, 디버그 및 소스 코드를 배포할 수 있도록 프로젝트, 웹 서비스 및 데이터베이스 및 기타 리소스에 대 한 참조입니다. Vspackage는 프로젝트 형식, 프로젝트 하위 형식 및 사용자 지정 도구를 제공 하 여 Visual Studio 프로젝트 시스템을 확장할 수 있습니다.  
  
 응용 프로그램을 만드는 함께 작동 하는 하나 이상의 프로젝트의 그룹화 하 여 솔루션에 프로젝트를 수집할 수도 있습니다. 솔루션에 관련 된 프로젝트 및 상태 정보는 두 개의 솔루션 파일, 텍스트 기반 솔루션 \(.sln\) 파일 및 이진 솔루션 사용자 옵션 \(.suo\) 파일에 저장 됩니다. 이러한 파일은 이전 버전의에 사용 된 그룹 \(.vbg\) 파일과 유사한 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], 작업 영역 \(.dsw\) 및 사용자 옵션 \(.opt\) 파일의 이전 버전에서 사용 되었던 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)]합니다.  
  
 자세한 내용은 [프로젝트](../../extensibility/internals/projects.md) 및 [솔루션](../../extensibility/internals/solutions.md)를 참조하세요.  
  
## 프로젝트 및 항목 템플릿  
 미리 정의 된 프로젝트 템플릿 및 프로젝트 항목 템플릿을 visual Studio에 포함 되어 있습니다. 사용자 고유의 템플릿을 만들 수도 또는 획득 하는 커뮤니티의 서식 파일을 다음 Visual Studio에 통합 합니다.[MSDN 코드 갤러리](http://code.msdn.microsoft.com/Project/ProjectDirectory.aspx?ProjectSearchText=visual%20studio) 템플릿 및 확장에 대 한 이동 하기에 적합 합니다.  
  
 템플릿은 특정 종류의 응용 프로그램, 컨트롤, 라이브러리 또는 클래스를 작성 하는 데 필요한 기본 파일과 프로젝트 구조를 포함 합니다. 유사한 템플릿 중 하나는 소프트웨어를 개발 하려는 경우 서식 파일을 기반으로 하는 프로젝트를 만들고 해당 프로젝트에서 파일을 수정 합니다.  
  
> [!NOTE]
>  이 템플릿 구조에 지원 되지 않습니다 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트입니다. 만드는 방법에 대 한 내용은 [!INCLUDE[vcprvc](../../debugger/includes/vcprvc_md.md)] 프로젝트 템플릿, 참조 [마법사 디자인](/visual-cpp/ide/designing-a-wizard)합니다.  
  
 자세한 내용은 [프로젝트 및 프로젝트 항목 템플릿 추가](../../extensibility/internals/adding-project-and-project-item-templates.md)을 참조하세요.  
  
## 속성 및 옵션  
 **속성** 단일 또는 여러 선택된 항목의 속성 창에 표시 됩니다: [속성 확장](../../extensibility/internals/extending-properties.md) 옵션 페이지에는 프로그래밍 언어 또는 VSPackage 등의 특정 구성 요소와 관련 된 옵션 집합을 포함: [옵션 및 옵션 페이지](../../extensibility/internals/options-and-options-pages.md)합니다. 설정은 일반적으로 UI 관련 기능을 가져오고 내보낼 수 있습니다: [사용자 설정에 대 한 지원](../../extensibility/internals/support-for-user-settings.md)합니다.  
  
## Visual Studio 서비스  
 서비스를 사용 하는 구성 요소에 대 한 인터페이스의 특정 집합을 제공 합니다. Visual Studio 확장을 비롯 한 모든 구성 요소에서 사용할 수 있는 서비스 집합을 제공 합니다. 예를 들어 Visual Studio 서비스를 표시 또는 도움말, 상태 표시줄 또는 UI 이벤트에 액세스할 수 있도록 동적으로 숨겨진 도구 창을 사용 합니다. 또한 Visual Studio 편집기 편집기 확장 하 여 가져올 수 있는 서비스를 제공 합니다. 자세한 내용은 [사용 하 고 서비스를 제공 합니다.](../../extensibility/using-and-providing-services.md)을 참조하세요.  
  
## 디버거  
 디버거는 사용자 인터페이스 언어 관련 디버깅 구성 요소입니다. 새 언어 서비스를 만든 경우에 특정 디버그 엔진에서 디버거를 연결을 만들 해야 합니다. 자세한 내용은 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)을 참조하십시오.  
  
## 소스 제어  
 소스 제어 플러그 인 또는 VSPackage를 구현 하는 방법에 대 한 정보를 참조 하십시오. [소스 제어](../../extensibility/internals/source-control.md)합니다.  
  
## 마법사  
 해당 형식의 새 프로젝트를 만들 때 사용자가 올바른 결정을 내릴 마법사 수 있도록, 새 프로젝트 유형으로는 마법사를 함께에서 만들 수 있습니다. 자세한 내용은 [마법사](../../extensibility/internals/wizards.md)을 참조하세요.  
  
## 사용자 지정 도구  
 사용자 지정 도구 도구 항목을 프로젝트에 연결 하 고 파일을 저장할 때마다 해당 도구를 실행할 수 있습니다. 자세한 내용은 [사용자 지정 도구](../../extensibility/internals/custom-tools.md)을 참조하세요.  
  
## VSSDK 유틸리티  
 VSSDK Vspackage의 다양 한 측면을 사용 하기 위해 필요할 수 있는 유틸리티 집합이 포함 되어 있습니다. 자세한 내용은 [VSSDK 유틸리티](../../extensibility/internals/vssdk-utilities.md)을 참조하세요.  
  
## Windows Installer를 사용 하 여  
 VSIX 설치 관리자를 사용 하지 않고 Windows Installer를 사용 하도록 할 수 있습니다: 레지스트리에 쓸 해야 하는 예를 들어 있습니다. 프로그램 확장과 함께 Windows Installer를 사용 하는 방법에 대 한 정보를 참조 하십시오. [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)합니다.  
  
## 도움말 뷰어  
 고유한 도움말 및 페이지 F1 도움말 뷰어를 통합할 수 있습니다. 자세한 내용은 [Microsoft 도움말 뷰어 SDK](../../extensibility/internals/microsoft-help-viewer-sdk.md)을 참조하세요.
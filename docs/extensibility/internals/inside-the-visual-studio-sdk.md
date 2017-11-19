---
title: "Visual Studio SDK 내 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- roadmap, Visual Studio integration SDK
- Visual Studio integration SDK roadmap
- integration roadmap, Visual Studio SDK
ms.assetid: 9118eaa4-0453-4dc5-9e16-c7062d254869
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ebba0ea11781a4b5a3d01aabb718b0ad778daab9
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="inside-the-visual-studio-sdk"></a>Visual Studio SDK 기본 사항
이 섹션에서는 Visual Studio 아키텍처, 구성 요소, 서비스, 스키마, 유틸리티 및 like를 포함 하 여 Visual Studio 확장에 대 한 자세한 정보를 제공 합니다.  
  
## <a name="extensibility-architecture"></a>확장성 아키텍처  
 다음 그림은 Visual Studio 확장성 아키텍처를 보여 줍니다. Vspackage는 서비스로 IDE 간에 공유 되는 응용 프로그램 기능을 제공 합니다. 표준 IDE에서는 다양 한 범위의 서비스와 같은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>, IDE 창 관리 기능에 대 한 액세스를 제공 합니다.  
  
 ![환경 아키텍처 그래픽](../../extensibility/internals/media/environment.gif "환경")  
Visual Studio 아키텍처의 일반화 된 보기  
  
## <a name="vspackages"></a>VSPackages  
 VSPackage는 UI 요소, 서비스, 프로젝트, 편집기 및 디자이너를 사용하여 Visual Studio를 구성 및 확장하는 소프트웨어 모듈입니다. Vspackage는 Visual Studio의 중앙 아키텍처 단위입니다. 자세한 내용은 참조 [Vspackage](../../extensibility/internals/vspackages.md)합니다.  
  
## <a name="visual-studio-shell"></a>Visual Studio Shell  
 Visual Studio 셸은 기본 기능을 제공 하 고 해당 구성 요소 Vspackage 및 MEF 확장 간 간 통신을 지원 합니다. 자세한 내용은 참조 [Visual Studio Shell](../../extensibility/internals/visual-studio-shell.md)합니다.  
  
## <a name="user-experience-guidelines"></a>사용자 환경 지침  
 Visual Studio에 대 한 새로운 기능을 디자인 계획을 디자인 및 사용 편의성 팁에 대 한 이러한 지침을 참조를 보는 것이 좋습니다: [Visual Studio 사용자 환경 지침](../../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
## <a name="commands"></a>명령  
 명령은 문서 인쇄, 보기 새로 고침 또는 새 파일 만들기 등의 작업을 수행하는 함수입니다.  
  
 Visual Studio를 확장 하는 경우 명령을 만들고 Visual Studio shell에 등록할 수 있습니다. 이러한 명령에서에서 어떻게 나타나는지 IDE, 예를 들어 메뉴 또는 도구 모음을 지정할 수 있습니다. 사용자 지정 명령에 표시 되는 일반적으로 **도구** 메뉴 및 도구 창을 표시 하기 위한 명령에 표시는 **다른 창** 의 하위 메뉴는 **보기** 메뉴.  
  
 명령을 만들 때도 만들어야 이벤트 처리기에 대 한 합니다. 이벤트 처리기 명령을 표시 또는 사용, 해당 텍스트를 수정할 수 있습니다 및가 활성화 된 경우 명령이 적절히 응답 하는지 보장 시기를 결정 합니다. 명령을 사용 하 여 IDE 대부분의 경우에서 처리는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스입니다. Visual Studio에서 명령은 가장 안쪽의 명령 컨텍스트부터 전역 선택 기반의 가장 바깥쪽 컨텍스트로 진행 하 고 로컬 선택을 기반으로 처리 됩니다. 주 메뉴에 추가된 명령은 즉시 스크립팅에 사용할 수 있습니다.  
  
 자세한 내용은 참조 [명령, 메뉴 및 도구 모음](../../extensibility/internals/commands-menus-and-toolbars.md)합니다.  
  
## <a name="menus-and-toolbars"></a>메뉴 및 도구 모음  
 메뉴 및 도구 모음 사용자가 명령을 호출할 수 있는 방법을 제공 합니다. 메뉴는 일반적으로 도구 창 위쪽에서 개별 텍스트 항목으로 표시 되는 명령의 행 이나 열 됩니다. 하위 메뉴는 작은 화살표를 포함 하는 명령을 클릭할 때 표시 되는 보조 메뉴가 있습니다. 상황에 맞는 메뉴에는 특정 UI 요소를 누를 때 나타납니다. 몇 가지 일반적인 메뉴 이름에는 **파일**, **편집**, **보기**, 및 **창**합니다. 자세한 내용은 참조 [확장 메뉴 및 명령을](../../extensibility/extending-menus-and-commands.md)합니다.  
  
 도구 모음 단추와 콤보 상자, 목록 상자 및 텍스트 상자 같은 다른 컨트롤의 행 이나 열 됩니다. 도구 모음 단추에 아이콘 이미지에 대 한 폴더 아이콘 등 일반적으로 필요는 **열려 있는 파일** 명령 또는 대 한 프린터는 **인쇄** 명령입니다. 모든 도구 모음 요소가 명령과 연결 합니다. 도구 모음 단추를 클릭 하면 연결 된 명령이 실행 됩니다. 드롭다운 목록 컨트롤의 경우 드롭 다운 목록에서 각 항목은 다른 명령과 연결 됩니다. Splitter 컨트롤 같은 일부 도구 모음 컨트롤은 하이브리드입니다. 컨트롤의 한 쪽은 도구 모음 단추 및 다른 쪽은 클릭할 때 몇 가지 명령을 표시 하는 아래쪽 화살표입니다.  
  
## <a name="tool-windows"></a>도구 창  
 도구 창은 정보를 표시 하려면 IDE에서 사용 됩니다. **도구 상자**, **솔루션 탐색기**, **속성** 창 및 **웹 브라우저** 은 도구 창의 예입니다.  
  
 도구 창은 일반적으로 사용자 작용할 수 있는 다양 한 컨트롤을 제공 합니다. 예를 들어,는 **속성** 창에는 사용자가 특정 목적으로 사용 되는 개체의 속성을 설정할 수 있습니다. **속성** 창 이므로 이런이 의미에서 특수 하지만 또한 일반적인 여러 가지 상황에서 사용할 수 있습니다. 마찬가지로,는 **출력** 창이 Visual Studio에서 많은 하위 시스템 Visual Studio 사용자에 게 출력을 제공 하는 데 사용할 수 있지만 일반 텍스트 기반 출력을 제공 하기 때문에 전문화 될 합니다.  
  
 여러 도구 창이 포함 된 Visual Studio의 다음 그림을 고려 합니다.  
  
 ![스크린 샷](../../extensibility/internals/media/t1gui.png "T1gui")  
  
 일부 도구 창은 함께 솔루션 탐색기 도구 창을 표시 하 고 다른 도구 창을 숨깁니다 하지만 탭을 클릭 하 여 사용할 수 있도록 하는 단일 창에 도킹 됩니다. 그림에는 나와 다른 두 개의 도구 창에는 **오류 목록** 및 **출력** 함께 단일 창에서 도킹 창.  
  
 또한 표시 된 다양 한 편집기 창을 표시 하는 주 문서 창이입니다. 도구 창에는 일반적으로 인스턴스를 하나만 필요는 없지만 (예를 들어 하나만 열 수 있습니다 **솔루션 탐색기**), 편집기 창에 도킹 되는 모두 있지만 별도 문서를 편집 하는 데 사용 되는 각각의 여러 인스턴스를 가질 수 있습니다 같은 창입니다. 그림에는 두 개의 편집기 창, 양식 디자이너 창을 두 개 및 시작 페이지를 표시 하는 브라우저 창이 있는 문서 창을 보여 줍니다. 문서 창에 있는 모든 창을 탭을 클릭 하 여 사용할 수 있지만 EditorPane.cs 파일을 포함 하는 편집기 창을 표시 되 고 활성화 합니다.  
  
 Visual Studio를 확장할 때 확장으로 Visual Studio 사용자가 수 있는 창이 상호 작용 하는 도구를 만들 수 있습니다. Visual Studio 사용자가 문서를 편집할 수 있도록 사용자 고유의 편집기를 만들 수 있습니다. 하므로 도구 창과 편집기는 Visual Studio에 통합 될 것을 도킹 하거나 탭에 올바르게 표시 하도록 프로그래밍 필요는 없습니다. Visual Studio에 올바르게 등록 된, 자동으로 갖게 됩니다 도구 창과 문서 창 Visual Studio에서의 일반적인 기능입니다. 자세한 내용은 참조 [확장 및 사용자 지정 도구 창의](../../extensibility/extending-and-customizing-tool-windows.md)합니다.  
  
## <a name="document-windows"></a>문서 창  
 문서 창에는 다중 문서 인터페이스 (mdi 다중) 창의 자식 프레임된 창이입니다. 문서 창 텍스트 편집기, 수 있는 폼 편집기 (라고도 디자이너) 또는 편집 컨트롤을 호스트 하기 일반적으로 사용 되지만 다른 기능 형식의 호스트할 수 있습니다. **새 파일** 대화 상자에는 문서 창은 Visual Studio에서 제공 하는 예가 포함 되어 있습니다.  
  
 대부분의 편집기는 프로그래밍 언어에 또는 HTML 페이지, 프레임, c + + 파일, 헤더 파일 등의 파일 형식에 적용 됩니다. 템플릿을 선택 하 고 **새 파일** 대화 상자에서 사용자를 동적으로 만듭니다 문서 창에서 템플릿과 연결 된 파일 형식에 대 한 편집기에 대 한 합니다. 사용자가 기존 파일을 열 때 문서 창이 만들어집니다.  
  
 문서 창을 사용해 서 MDI 클라이언트 영역으로 제한 됩니다. 바탕 화면에서 각 문서 창에는 탭 및 탭 순서 MDI 영역에 열려 있을 수 있는 다른 창에 연결 됩니다. 여러 개의 가로 또는 세로 탭 그룹을 사용해 서 MDI 영역을 분할 하는 옵션이 포함 된 바로 가기 메뉴를 표시 문서 창의 탭을 마우스 오른쪽 단추로 클릭 합니다. MDI 영역을 분할 여러 파일을을 동시에 볼 수 있습니다. 자세한 내용은 참조 [문서 창을](../../extensibility/internals/document-windows.md)합니다.  
  
## <a name="editors"></a>편집기  
 Visual Studio 편집기를 사용 하면 사용자 지정 하 고 관리 되는 확장성 프레임 워크 (MEF)를 사용 하 여 콘텐츠 유형에 사용할 수 있습니다. 대부분의 경우에서 (예를 들어 메뉴 명령 또는 바로 가기 키) 셸에서 기능을 포함 하려는 경우 MEF 확장을 VSPackage와 결합할 수 있습니다는 편집기를 확장 하기 위해 VSPackage 만들도록 않아도 됩니다.  
  
 예를 들어 사용자 지정 편집기를 읽기 / 쓰기 데이터베이스를 하려는 경우 또는 디자이너를 사용 하려는 경우에 만들 수 있습니다. 예: 메모장 또는 Microsoft 워드 패드 외부 편집기를 사용할 수 있습니다. 자세한 내용은 참조 [편집기와 언어 서비스 확장](../../extensibility/editor-and-language-service-extensions.md)합니다.  
  
## <a name="language-services"></a>언어 서비스  
 새 프로그래밍 키워드 또는 새 프로그래밍 언어도 지원 하기 위해 Visual Studio 편집기를 사용 하도록 하려는 경우 언어 서비스를 만듭니다. 각 언어 서비스는 완벽 하 게, 부분적으로, 또는 전혀 특정 편집기 기능을 구현할 수 있습니다. 구성 방법에 따라 언어 서비스 구문 강조, 중괄호 일치, IntelliSense 지원 및 편집기의 다른 기능을 제공할 수 있습니다.  
  
 언어 서비스의 핵심 파서와 스캐너 됩니다. 스캐너 (또는 렉서) 소스 파일 토큰, 이라고 하는 요소로 나누고 한 파서 이러한 토큰 간의 관계를 설정 합니다. 언어 서비스를 만들 때 Visual Studio는 토큰 및 언어의 문법을 알 수 있도록 파서와 스캐너 구현 해야 합니다. 관리 되거나 관리 되지 않는 언어 서비스를 만들 수 있습니다. 자세한 내용은 참조 [레거시 언어 서비스 확장성](../../extensibility/internals/legacy-language-service-extensibility.md)합니다.  
  
## <a name="projects"></a>프로젝트  
 Visual Studio에서 프로젝트는 개발자가 구성 하 고 빌드 소스 코드 및 기타 리소스를 사용 하는 컨테이너입니다. 프로젝트를 통해 구성, 빌드, 디버깅 및 소스 코드를 배포, 웹 서비스 및 데이터베이스를 다른 리소스에 대 한 참조입니다. Vspackage는 프로젝트 형식, 프로젝트 하위 형식 및 사용자 지정 도구를 제공 하 여 Visual Studio 프로젝트 시스템을 확장할 수 있습니다.  
  
 프로젝트 그룹을 응용 프로그램을 만드는 함께 작동 하는 하나 이상의 프로젝트를 솔루션으로 수집할 수 수 있습니다. 솔루션에 관련 된 프로젝트 및 상태 정보는 두 개의 솔루션 파일, 텍스트 기반 솔루션 (.sln) 파일 및 이진 솔루션 사용자 옵션 (.suo) 파일에 저장 됩니다. 이러한 파일은 이전 버전의 사용 된 그룹 (.vbg) 파일과 유사한 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], 작업 영역 (.dsw) 및 사용자 옵션 (.opt) 파일의 이전 버전에서 사용 되었던 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)]합니다.  
  
 자세한 내용은 참조 [프로젝트](../../extensibility/internals/projects.md) 및 [솔루션](../../extensibility/internals/solutions.md)합니다.  
  
## <a name="project-and-item-templates"></a>프로젝트 및 항목 템플릿  
 Visual Studio에는 미리 정의 된 프로젝트 템플릿 및 프로젝트 항목 템플릿이 포함 되어 있습니다. 사용자 고유의 템플릿을 만들 수도 하 고 또는 커뮤니티에서 서식 파일을 설정 하 고, 다음 Visual Studio에 통합 수입니다. [MSDN 코드 갤러리](http://code.msdn.microsoft.com/Project/ProjectDirectory.aspx?ProjectSearchText=visual%20studio) 서식 파일 및 확장에 대 한 이동 하기에 적합 합니다.  
  
 템플릿은 특정 종류의 응용 프로그램, 컨트롤, 라이브러리 또는 클래스를 작성 하는 데 필요한 기본 파일과 프로젝트 구조를 포함 합니다. 서식 파일 중 하 나와 유사한 소프트웨어 개발 하려는 경우 서식 파일을 기반으로 하는 프로젝트를 만들고 해당 프로젝트에서 파일을 수정 합니다.  
  
> [!NOTE]
>  이 템플릿 구조에 지원 되지 않습니다 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트. 만드는 방법에 대 한 내용은 [!INCLUDE[vcprvc](../../code-quality/includes/vcprvc_md.md)] 프로젝트 템플릿, 참조 [마법사 디자인](/cpp/ide/designing-a-wizard)합니다.  
  
 자세한 내용은 참조 [추가 프로젝트 및 프로젝트 항목 템플릿](../../extensibility/internals/adding-project-and-project-item-templates.md)합니다.  
  
## <a name="properties-and-options"></a>속성 및 옵션  
 **속성** 단일 또는 여러 선택된 항목의 속성 창에 표시 됩니다: [확장 속성](../../extensibility/internals/extending-properties.md) 옵션 페이지와 같은 특정 구성 요소와 관련 된 옵션의 집합을 포함 한 프로그래밍 언어 또는 VSPackage: [옵션 및 옵션 페이지](../../extensibility/internals/options-and-options-pages.md)합니다. 설정은 일반적으로 UI 관련 된 기능을 가져오고 내보낼 수 있습니다: [사용자 설정에 대 한 지원을](../../extensibility/internals/support-for-user-settings.md)합니다.  
  
## <a name="visual-studio-services"></a>Visual Studio 서비스  
 서비스를 사용할 구성 요소에 대 한 인터페이스의 특정 집합을 제공 합니다. Visual Studio 확장을 포함 한 모든 구성 요소에서 사용할 수 있는 서비스를 제공 합니다. 예를 들어 Visual Studio 서비스를 표시 또는 도움말, 상태 표시줄 또는 UI 이벤트에 액세스할 수 있도록 동적으로 숨겨진 도구 창을 사용 합니다. Visual Studio 편집기는 또한 편집기 확장 하 여 가져올 수 있는 서비스를 제공 합니다. 자세한 내용은 참조 [사용 및 서비스 제공](../../extensibility/using-and-providing-services.md)합니다.  
  
## <a name="debugger"></a>디버거  
 디버거는 사용자 인터페이스 언어 관련 디버깅 구성 요소입니다. 새 언어 서비스를 만든 경우에에서 디버거를 연결 하는 특정 디버그 엔진을 만들 해야 합니다. 자세한 내용은 참조 [Visual Studio 디버거 확장성](../../extensibility/debugger/visual-studio-debugger-extensibility.md)합니다.  
  
## <a name="source-control"></a>소스 제어  
 소스 제어 플러그 인 또는 VSPackage를 구현 하는 방법에 대 한 정보를 참조 하십시오. [소스 제어](../../extensibility/internals/source-control.md)합니다.  
  
## <a name="wizards"></a>마법사  
 마법사를 통해 수 있도록 사용자가 해당 유형의 새 프로젝트를 만들 때 올바른 결정을 확인 하는, 새 프로젝트 형식으로는 마법사를 함께에서 만들 수 있습니다. 자세한 내용은 참조 [마법사](../../extensibility/internals/wizards.md)합니다.  
  
## <a name="custom-tools"></a>사용자 지정 도구  
 사용자 지정 도구를 사용 하 여 프로젝트에서 항목 도구 연결 하 고 파일을 저장할 때마다 해당 도구를 실행할 수 있도록 합니다. 자세한 내용은 참조 [사용자 지정 도구](../../extensibility/internals/custom-tools.md)합니다.  
  
## <a name="vssdk-utilities"></a>VSSDK 유틸리티  
 VSSDK은 Vspackage의 다양 한 측면을 사용 하려면 필요할 수 있는 유틸리티 집합이 포함 되어 있습니다. 자세한 내용은 참조 [VSSDK 유틸리티](../../extensibility/internals/vssdk-utilities.md)합니다.  
  
## <a name="using-windows-installer"></a>Windows Installer를 사용 하 여  
 VSIX 설치 보다는 Windows Installer를 사용 하도록 할 수 있습니다: 예를 들어 레지스트리에 쓰기를 할 수 있습니다. Windows Installer를 사용 하 여 확장 프로그램을 사용 하는 방법에 대 한 정보를 참조 하십시오. [Windows Installer와 Vspackage 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)합니다.  
  
## <a name="help-viewer"></a>도움말 뷰어  
 사용자 고유의 도움말 및 페이지 F1 도움말 뷰어를 통합할 수 있습니다. 자세한 내용은 참조 [Microsoft 도움말 뷰어 SDK](../../extensibility/internals/microsoft-help-viewer-sdk.md)합니다.
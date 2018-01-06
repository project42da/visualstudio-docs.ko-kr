---
title: "사용 가능한 서비스 목록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- services, Visual Studio
- Visual Studio, services
ms.assetid: 724eb24b-b87c-4971-a2e7-adee7afc03b2
caps.latest.revision: "49"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 50016483ea1fa5a04c41e49493eda92b6a270b8c
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="list-of-available-services"></a>사용 가능한 서비스 목록
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]및 Visual Studio SDK는 다음 서비스를 지원 합니다. 여기 나열 되지 않은 자신의 서비스를 제공 하는 일부 패키지-예를 들어 언어 서비스는 단일 서비스가 없는 GUID입니다. 레지스트리에서 언어 서비스의 GUID를 찾을 수 언어의 이름을 사용 해야 합니다.  
  
 여기에 나열 된 또는 다른 소스 (예를 들어 언어 서비스)에서 가져온 서비스 Guid를 사용 하 여 기본 인터페이스 또는 각 서비스에 표시 된 인터페이스를 가져올 수 있습니다.  
  
## <a name="the-services"></a>서비스  
  
|서비스|인터페이스|Visual Studio|Visual Studio 2005|설명|  
|-------------|---------------|-------------------|------------------------|-----------------|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SBindHost>|<xref:Microsoft.VisualStudio.OLE.Interop.IBindHost>|예|예|Vspackage을 가져오는 데 사용 된 <xref:Microsoft.VisualStudio.OLE.Interop.IBindHost> 비동기 데이터 전송을 용이 하 게 하려면 ActiveX 컨트롤의 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SDTE>|<xref:EnvDTE.DTE>|아니요|예|자동화에 사용 되는 확장성 DTE (디자인 타임) 개체를 가져옵니다.<br /><br /> C/C + + ID: SID_SDTE|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SCodeNavigate>|<xref:Microsoft.VisualStudio.Shell.Interop.ICodeNavigate>|예|예|컨트롤에 대 한 기본 이벤트 처리기를 표시 하려면 폼 디자이너에 의해 구현 됩니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SContainerDispatch>|IDispatch|예|예|다른 VSPackage 나 컨트롤의 자동화 인터페이스에 액세스 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SExtendedTypeLib>|<xref:Microsoft.VisualStudio.Shell.Interop.IExtendedTypeLib>|예|예|VSPackage를 추가 하거나 확장 된 형식 라이브러리를 만들 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SDirList>|<xref:Microsoft.VisualStudio.Shell.Interop.IDirList>|아니요|예|목록의 목록; 명명 된 컨테이너에 대 한 액세스를 제공 합니다. 예를 들어에 나와 있는 것 처럼 검색 하는 디렉터리 목록은 **찾기 및 바꾸기** 대화 상자에는 **찾는 위치** 드롭 다운 목록입니다. <xref:Microsoft.VisualStudio.Shell.Interop.IDirList> 개체 수에서 읽을 뿐만 수에 기록 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SIVsPackageDynamicToolOwner>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPackageDynamicToolOwner>|예|예|VSPackage를 자체 도구 창을 동적으로 표시 하거나 숨길 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SLicensedClassManager>|<xref:Microsoft.VisualStudio.Shell.Interop.ILicensedClassManager>|예|예|VSPackage에 지정할 수 있도록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 라이선스 키 목록을 지정 하 여 필요한 클래스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SLocalRegistry>|<xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry2>|예|예|로컬 기준으로 레지스트리를 액세스 하기 위해 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 레지스트리 하이브입니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SOleComponentManager>|<xref:Microsoft.VisualStudio.OLE.Interop.IOleComponentManager>|예|예|메시지 루프, 키보드 루프 및 이벤트 알림 등의 구성 요소를 조정 서비스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SOleComponentUIManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IOleComponentUIManager>|예|예|다양 한 사용자 인터페이스 (UI) 요소에 액세스 하기 위해 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], UI 이벤트, 도움말 및 상태 표시줄, 등입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SOleInPlaceComponent>|<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponent>|예|예|UI의 UI와 통합 하기 위해 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SOleInPlaceComponentSite>|<xref:Microsoft.VisualStudio.Shell.Interop.IOleInPlaceComponentSite>|예|예|VSPackage를 도구와 관련 된 UI 변경 내용을 제어할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.OLE.Interop.SOleUndoManager>|<xref:Microsoft.VisualStudio.OLE.Interop.IOleUndoManager>|예|예|해당 컨테이너의 실행 취소 스택에 참여 하거나 하거나 해당 컨테이너의 실행 취소 스택에 액세스 하는 컨테이너의 실행 취소 관리자에 액세스 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SProfferService>|<xref:Microsoft.VisualStudio.Shell.Interop.IProfferService>|예|예|고유 서비스를 제공 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SProfferTypeLib>|<xref:Microsoft.VisualStudio.Shell.Interop.IProfferTypeLib>|예|예|형식 라이브러리를 참조할 수 있도록 forms 디자이너를 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.STrackSelection>|<xref:Microsoft.VisualStudio.Shell.Interop.ITrackSelection>|예|예|선택 컨테이너에서 선택한 항목에 대 한 액세스를 제공합니다. Forms 디자이너에서 사용합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SUIHostCommandDispatcher>|<xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget>|예|예|명령 처리기 체인에 참여 하 고 자체 또는 통합된 개발 환경 (IDE) 대신 하 여 명령을 처리 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SUIHostLocale>|<xref:Microsoft.VisualStudio.Shell.Interop.IUIHostLocale>|예|예|호스트의 UI 로캘 정보에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>|아니요|예|로깅이 설정 되는 경우 상위 수준 메시지를 기록 하기 위해 VSPackage를 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsAddProjectItemDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAddProjectItemDlg>|예|예|에 대 한 액세스를 제공 된 **프로젝트 항목 추가** 대화 상자를 구현 하는 Vspackage가 자신의 **항목 추가** 메뉴 옵션입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsAddWebReferenceDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAddWebReferenceDlg>|예|예|표시는 **참조 추가** 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsAppCommandLine>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAppCommandLine>|예|예|Devenv.exe 명령줄 스위치를 지정한 경우를 결정 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCallBrowser>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCallBrowser>|아니요|예|새로 만들 수는 VSPackage를 사용 하면 **호출 브라우저** 디버깅에 사용 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsClassView>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsClassView>|예|예|동기화 하는 VSPackage를 사용 하면는 **클래스 뷰** 특정 개체입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCmdNameMapping>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCmdNameMapping>|예|예|명령 이름을 Guid 및 백에 매핑 및 모든 사용 가능한 명령 및 이름의 이름 확인에 대 한 지원을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCodeDefView>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCodeDefView>|아니요|예|조작 하기 위해 VSPackage를 사용 하도록 설정 된 **코드 정의 보기**합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCodeShareHandler>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCodeShareHandler>|예|예|내부 서비스입니다. 사용하지 마십시오.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsCodeWindow>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindow>|예|예|하나 이상의 문서가 포함 될 수 있는 코드 창에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsCodeWindowManager>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsCodeWindowManager>|예|예|드롭다운 표시줄 등 코드 창에 변경 사항을 추가 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCommandWindow>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCommandWindow><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsCommandWindow2>|예|예|명령을 실행 하기 위해 VSPackage를 사용 하도록 설정 된 **명령 창** 작용할는 **명령 창**합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCommandWindowsCollection>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCommandWindowsCollection>|아니요|예|목록을 조작 하기 위해 VSPackage를 사용 하면 **명령** 에서 windows 유지 관리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsComplusLibrary>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsLibraryReferenceManager>|예|예|찾아보기 정보를 제공 하기 위해 VSPackage를 사용 하도록 설정 된 **개체 브라우저**합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsComponentSelectorDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsComponentSelectorDlg>|아니요|예|지원 하기 위해 VSPackage를 사용 하도록 설정 된 **참조 추가** 옵션을 사용 하면 사용자는 프로젝트에 추가할 외부 구성 요소입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsComponentSelectorDlg2>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsComponentSelectorDlg2>|아니요|예|지원 하기 위해 VSPackage를 사용 하도록 설정 된 **참조 추가** 옵션을 사용 하면 사용자는 프로젝트에 추가할 외부 구성 요소입니다. 이 버전의 대화 상자 표시 되기 전에의 구성 요소 목록을 미리 채울 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsConfigurationManagerDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsConfigurationManagerDlg>|아니요|예|표시는 **Configuration Manager** 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsCreateAggregateProject>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsCreateAggregateProject>|아니요|예|VSPackage의 다른 프로젝트 컬렉션을 포함 하는 프로젝트를 만들 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsDebuggableProtocol>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProtocol>|예|예|특정 디버그 엔진을 시작 하는 IDE에서 사용 되는 디버깅할 수 있는 프로토콜의 목록을 업데이트 하는 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsDebugLaunch>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugLaunch>|예|예|디버거 시작을 지원 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsDiscoveryService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDiscoveryService>|예|예|VSPackage는 웹 서비스를 검색 하는 데 사용 되는 검색 세션을 만들 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsEnumHierarchyItemsFactory>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumHierarchyItemsFactory>|예|예|만들기 위한 팩터리를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.IVsEnumHierarchyItemsFactory> 전체를 열거 하는 데 사용 하는 개체 계층 구조 (프로젝트)를 지정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsErrorList>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsErrorList>|아니요|예|조작 하기 위한 추가 메서드를 제공는 **빌드 오류 목록** 작업 창. 특히, 표시는 **빌드 오류 목록** 은 forefront에 작업 창 고 강제로 모든 오류가 표시 됩니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsExternalFilesManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsExternalFilesManager>|예|예|에 대 한 액세스를 제공 된 **기타 파일** 현재 솔루션의 프로젝트 노드.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChange>||예|예|사용되지 않습니다. 사용 하 여 `SVsFileChangeEx` 대신 서비스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFileChangeEx>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFileChangeEx>|예|예|IDE에 의해 트리거되는 다양 한 파일 변경 이벤트에 액세스 하는 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFilterAddProjectItemDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterAddProjectItemDlg>|예|예|에 표시 되는 항목을 필터링 하기 위해 VSPackage를 사용 하도록 설정 된 **항목 추가** 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFilterKeys>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFilterKeys>|예|예|고급 키보드 필터링을 수행 하기 위해 VSPackage를 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFontAndColorCacheManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorCacheManager>|아니요|예|글꼴에 대 한 캐시 집합에 대 한 액세스를 제공 하 고에 색을 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 새로 고치거 나 특정 선택 취소 캐시 또는 모든 캐시 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsFontAndColorStorage>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorStorage><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsFontAndColorUtilities>|예|예|유지 관리 하는 글꼴 및 색 설정을 조작 하는 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 또한이 서비스의 글꼴 및 색 데이터를 조작 하기 위한 유틸리티 메서드 컬렉션에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsGeneralOutputWindowPane>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindowPane>|예|예|에 일반 액세스를 제공 **출력 창** 창에서 필요에 따라 작성 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsHelpService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHelpSystem>|예|예|도움말 시스템에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsHTMLConverter>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsHTMLConverter>|예|예|사용 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 해당 출력의 서식을 지정 하려면 HTML 핸들에는 디버거 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIME>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIME>|예|예|에 (입력기) API에서 VSPackage에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntegratedHelp>|<xref:Microsoft.VisualStudio.VSHelp.SVsHelp>|예|예|에 대 한 액세스를 제공 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 도움말 키워드 또는 URL에 대 한 시스템 탐색 컨트롤 및 도움말 파일을 통해 액세스 합니다. 이 서비스를 도움말에 통합 하는 경우에 사용할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 외부 프로그램으로 실행 하지 않는 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntelliMouseHandler>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntelliMouseHandler>|예|예|마우스 휠을 사용 하 고 마우스 휠을 클릭할 때 이동 및 스크롤 비트맵을 처리 하는 등의 IntelliMouse 기능에 액세스 하는 VSPackage를 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntellisenseEngine>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseEngine>|아니요|예|프로젝트 계층 노드를를 로드 하거나 IntelliSense 작업에 대 한 지원의 일부로 파일을 언로드할 수 있습니다. 프로세스 로드 하 고 언로드하는 프로젝트에 대 한 IntelliSense 도구 설명에 표시 되는 내용에 영향을 줄 수 있는 트리거 이벤트입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntellisenseProjectHost>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProjectHost>|아니요|예|중첩 된 IntelliSense 프로젝트에 대 한 정보를 제공 하는 프로젝트 계층 구조 노드를 사용 하도록 설정 (구현 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProject> 인터페이스)는 IntelliSense 도구 설명에 표시할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsIntellisenseProjectManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsIntellisenseProjectManager>|아니요|예|참조 또는 IntelliSense 도구 설명에 표시 되는 내용에 영향을 줄 수 있는 구성으로 변경 하는 이벤트의 수신기를 알리기 위해 프로젝트 계층 구조 노드를 수 있습니다. 포함 된 언어와 함께 사용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsInvisibleEditorManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsInvisibleEditorManager>|예|예|즉, "보이지 않는" 편집기를 등록 하려면 사용자에 게 표시 되지 않으면 전체 편집 기능을 제공 하는 편집기는 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsLanguageFilter>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextViewFilter>|예|예|데이터 팁 같은 텍스트 보기 및 단어의 범위에 대 한 추가 정보를 제공 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsLaunchPad>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsLaunchPad>|예|예|임시 일괄 처리, 스크립트를 실행할 해당 출력은 출력 창으로 전송 명령줄 프로그램을 실행 하 고 표준 경고 및 오류 창에 전송 된 오류 메시지를 구문 분석 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsLaunchPadFactory>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsLaunchPadFactory>|예|예|만들기 위한 팩터리를 제공 <xref:Microsoft.VisualStudio.Shell.Interop.IVsLaunchPad> 개체입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsLinkedUndoTransactionManager>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsLinkedUndoTransactionManager>|예|예|연결 된 실행 취소 관리자에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsMenuEditor>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMenuEditorFactory>|예|예|공유 메뉴 편집기에 액세스 하려면 forms 디자이너를 사용 하도록 설정 합니다. IVsMenuEditorFactory 쿼리할 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsMenuEditor>합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsMonitorUserContext>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorUserContext>|예|예|VSPackage는 "컨텍스트 모음"에 특정 컨텍스트에 대 한 도움말 키워드를 연결 하는 데 사용 되는 만들려는 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjBrowser>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjBrowser>|예|예|특정 개체를 이동 하기 위해 VSPackage를 사용 하도록 설정 된 **개체 브라우저**합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectManager>|예|예|해당 라이브러리 관리자를 등록 하기 위해 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 는 네임 스페이스, 클래스 및 열거형 등의 개체를 관리 하기 위한 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsObjectSearch>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsObjectSearch>|예|예|VSPackage는 특정 개체를 검색할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsOpenProjectOrSolutionDlg>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOpenProjectOrSolutionDlg>|아니요|예|표준을 사용 하기 위해 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 대화 상자를 프로젝트 또는 솔루션을 엽니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsOutputWindow>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsOutputWindow>|예|예|일반 출력 창에 추가 출력 창을 만들려면 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsParseCommandLine>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsParseCommandLine>|예|예|구현자를 사용 하도록 설정 된 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 명령줄 구문 분석 하는 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsPathVariableResolver>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPathVariableResolver>|아니요|예|관련 된 변수를 확인 하는 방법을 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 최종 경로 생성 하는 경로에 포함 된 하 고 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsPreviewChangesService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPreviewChangesService>|아니요|예|표시는 **변경 내용 미리 보기** 코드를 리팩터링 하는 데 사용 되는 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsProfileDataManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProfileDataManager>|아니요|예|프로필 관리자에 대 한 액세스를 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 가져오기 및 설정 데이터를 내보내는으로 현재 사용자의 프로필 설정의 UI를 표시할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsProfilesManagerUI>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsProfilesManagerUI>|아니요|예|현재 사용자의 프로필 설정을 보여 주는 대화 상자를 표시 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsPropertyPageFrame>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPropertyPageFrame>|예|예|재정의 속성 페이지에 처음에 표시 되는 VSPackage를 사용 하도록 설정 된 **속성** 창.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|아니요|예|메모리에서 변경 되거나 저장 될 파일은 소스 제어 공급자를 알리기 위해 Vspackage에서 사용 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterDebugTargetProvider>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectDebugTargetProvider>|아니요|예|VSPackage 프로젝트를를 프로그래밍 방식으로 디버거를 시작 하도록 대상을 재정의할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterEditors>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterEditors>|예|예|IDE와 편집기 팩터리를 등록 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsRegisterFindScope>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsRegisterFindScope>|아니요|예|에 대 한 검색 범위를 등록 하기 위해 VSPackage를 사용 하도록 설정 된 **파일에서 찾기** 대화 상자.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterPriorityCommandTarget>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterPriorityCommandTarget>|예|예|VSPackage를 모든 명령을 확인 하기 위해 VSPackage를 허용 하는 우선 순위가 높은 명령 처리기를 자체 등록할 수 있습니다. 가능 하면 자주,를 사용 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRegisterProjectTypes>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterProjectTypes>|예|예|프로젝트 형식을 IDE에 등록 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsResourceManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsResourceManager>|아니요|예|위성 Dll에서에서 스레드와 관리 되지 않는 리소스를 로드 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsResourceView>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsResourceView>|예|예|사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsClassView> 대신 서비스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsRunningDocumentTable>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRunningDocumentTable>|예|예|연 문서에는 IDE의 실행 중인 문서 테이블 RDT () 현재 모두 추적 하는 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|아니요|예|소스 제어에 참여할 수 있도록 자신을 원본 제어 공급자를 등록 하는 Vspackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSccToolsOptions>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions>|예|예|VSPackage를 가져오고 소스 제어 공급자 옵션을 설정할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSettingsReader>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSettingsReader>|아니요|예|사용자의 프로필 설정에 대 한 읽기 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsShell>|예|예|다른 Vspackage 조작와 직접 상호 작용 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellDebugger>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsDebugger>|예|예|에 대 한 액세스를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShellMonitorSelection>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsMonitorSelection>|예|예|VSPackage를 현재 선택 영역을 액세스 하 고 명령 UI 컨텍스트를 관리할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDCodeDomProvider>|IVSMDCodeDomProvider|아니요|예|네이티브 코드에서 사용할 수 있는 코드 문서 개체 모델 (DOM) 공급자에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDDesignerService>|IVSMDCodeDomCreator<br /><br /> IVSMDDesignerService|아니요|예|관리 되는 양식 디자이너에 대 한 IDE의 지원에 대 한 액세스를 제공합니다. `IVSMDCodeDomCreator` DOM 공급자 코드를 만드는 데 사용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDPropertyBrowser>|IVSMDPropertyBrowser|아니요|예|디자이너 속성 windows 서비스에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVSMDTypeResolutionService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVSMDTypeResolutionService>|아니요|예|반환할 수 있는 인터페이스에 액세스할 수는 <xref:System.ComponentModel.Design.ITypeResolutionService> 네이티브 코드에서 사용할 수 있는 개체입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSmartOpenScope>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSmartOpenScope>|아니요|예|필요에 따라 잠금 점을 고려 하는 어셈블리에서 범위 열 방법을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution>|예|예|현재 솔루션에 대 한 최상위 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionBuildManager>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager>|예|예|솔루션의 빌드 프로세스와 상호 작용 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionObject>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution>|예|예|사용 하 여 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution> 대신 서비스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolutionPersistence>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>|예|예|VSPackage를 저장 하 고 현재 솔루션의.sln 파일에서 정보를 검색할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSQLCLRReferences>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSQLCLRReferences>|아니요|예|기능을 제공 추가 하 고 관리 코드 어셈블리의 참조를 업데이트 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStartPageDownload>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStartPageDownload>|아니요|예|시작 페이지의 다운로드 서비스 시작 및 백그라운드 스레드 다운로드 서비스 중지에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStatusbar>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStatusbar>|예|예|IDE의 상태 표시줄에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStrongNameKeys>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStrongNameKeys>|아니요|예|관리 코드 어셈블리에 서명 하는 데 사용 되는 암호에 강력한 키 이름 및 키 파일을 만드는 방법에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsStructuredFileIO>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsStructuredFileIO>|예|예|여러 형식의 데이터를 저장 하기 위한 지원을 제공 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTaskList>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTaskList>|예|예|작업 목록 창에서 IDE의 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextImageUtilities>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextImageUtilities>|아니요|예|로드 하 고 텍스트 파일 저장에 대 한 유틸리티를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextManager>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextManager><br /><br /> <xref:Microsoft.VisualStudio.TextManager.Interop.IVsHiddenTextManager>|예|예|IDE에서 사용할 수 있는 숨겨진된 텍스트 세션 (영역에 대 한 숨겨진) 뿐만 아니라 모든 텍스트 버퍼에 대 한 액세스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTextOut>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTextOut>|예|예|에 Win32 버전 `TextOut` 디바이스 컨텍스트 (DC 핸들 필요)에 텍스트 쓰기에 대 한 함수입니다.|  
|<xref:Microsoft.VisualStudio.TextManager.Interop.SVsTextSpanSet>|<xref:Microsoft.VisualStudio.TextManager.Interop.IVsTextSpanSet>|예|예|텍스트 이미지 또는 버퍼에서 텍스트 범위는 목록에 대 한 액세스를 제공합니다. 이 서비스는 일반적으로 문서 컨테이너에 구현과 현재 문서를 나타냅니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsThreadedWaitDialog>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsThreadedWaitDialog>|아니요|예|(백그라운드 작업을 위해 대기 하는 데 사용) 하는 다른 스레드에서 대기 하는 대화 상자를 표시 하기 위해 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsThreadPool>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsThreadPool>|아니요|예|다음에서 유지 관리 하는 백그라운드 작업을 시작 하기 위해 VSPackage를 사용 하면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolbox>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolbox>|예|예|IDE의에 액세스를 제공 **도구 상자**합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolboxActiveXDataProvider>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProvider>|예|예|VSPackage에서 정보를 얻을 수 있도록 **도구 상자** 항목입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolboxDataProviderRegistry>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolboxDataProviderRegistry>|아니요|예|전체 미리 로드 하는 성능 비용이 발생 하지 않고 도구 상자 데이터 공급자를 등록 하기 위해 VSPackage를 사용 하면 **도구 상자**합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsToolsOptions>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsToolsOptions>|아니요|예|여부를 확인 하는 VSPackage를 사용 하면는 **옵션** 대화 상자를 열어 모든 옵션 페이지의 표시 여부를 새로 고칠 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2><br /><br /> <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3>|아니요|예|VSPackage는 프로젝트 파일의 변경 내용을 모니터링 하 고 소스 제어 공급자를 통해 일괄 처리를 제어할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackSelectionEx>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackSelectionEx>|예|예|현재 선택한 프로젝트 항목에 영향을 줄 수 있는 선택 항목에 대 한 변경의 IDE를 알리기 위해 VSPackage를 사용 하도록 설정 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIHierWinClipboardHelper>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIHierWinClipboardHelper>|예|예|다른 계층 구조를 클립보드의 사용을 조정 하는 계층 구조를 (예: VSPackage 프로젝트)를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShell>|예|예|도구 창과 문서 창 같은 IDE의 UI 요소에 대 한 액세스를 제공합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellDocumentWindowMgr>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellDocumentWindowMgr>|예|예|VSPackage를 데이터 스트림의 내용을 기반으로 하는 모든 창의 위치를 복원 하거나 모든 창의 위치를 스트림에 저장할 수 있습니다. 거의 사용 되지 않습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShellOpenDocument>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument>|예|예|여러 가지 방식으로 문서를 열고 하 고는 문서를 소유한 사람을 결정 하는 VSPackage를 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger>|아니요|예|구현자에 의해 사용 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory> 보고서 오류 및 정보 메시지에 대 한 인터페이스입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebBrowsingService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebBrowsingService>|예|예|VSPackage를 만들고 웹 검색 세션을 제어할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebFavorites>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebFavorites>|예|예|사용자에 게 추가 하기 위해 VSPackage를 사용 하면 **즐겨찾기** 목록입니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebPreview>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebPreview>|예|예|VSPackage를 자식 창에 일반적으로 웹 페이지를 미리 볼 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWebURLMRU>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWebURLMRU>|예|예|VSPackage를 Url mru (가장 최근에 사용 됨) 목록에 URL을 추가 하 고 MRU 목록의 모든 Url 목록을 가져올 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsWindowFrame>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsWindowFrame>|예|예|VSPackage는 패키지 또는 패키지의 일부가 될 수 있습니다 수 설정 된 위치에 창 프레임을 가져올 수 있습니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsXMLMemberIndexService>|<xref:Microsoft.VisualStudio.Shell.Interop.IVsXMLMemberIndexService>|예|예|특정 메타 데이터 파일에 연결 된 XML 형식 문서 파일에 대 한 액세스를 제공 합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [COM 및 관리 되는 서비스](http://msdn.microsoft.com/en-us/6c5808b4-ad87-48d7-ae06-33a81e7052af)   
 [서비스 사용 및 제공](../../extensibility/using-and-providing-services.md)
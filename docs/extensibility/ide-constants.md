---
title: "IDE 상수 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- IDE, errors
- logical views
- errors [Visual Studio], IDE
- UI context constants
- constants, Visual Studio IDE
- IDE, constants
- physical views
ms.assetid: 5030e70a-241d-474a-ba8c-e3b1cf947ff0
caps.latest.revision: "23"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4a43bc68a87d00dcce90f1a948b64dd786e9b440
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ide-constants"></a>IDE 상수
<xref:Microsoft.VisualStudio.VSConstants> 클래스는 통합된 개발 환경 (IDE) 관련 된 같고 헤더 파일에만 이전에 정의 된 상수를 제공 합니다.  
  
## <a name="logical-and-physical-views"></a>논리 / 물리 뷰  
  
|값|설명|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Code>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` 이 값을 전달 해야 하는 처리기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 가져올 메서드를는 **프로그램** 가능한 코드 보기에이 경우에서 대화 상자.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Debugging>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` 이 값을 전달 하는 처리기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 가져올 메서드를는 **연결 프로그램** 대화 상자에서 가능한 여기 채워진 <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Debugging> 동일한 뷰를 매핑되는 뷰 디버깅 <xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Code>합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Designer>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` 이 값을 전달 하는 처리기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 가져올 메서드를는 **프로그램** 대화 상자에이 예에서 **양식 보기** 디자이너 보기.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_Primary>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` 이 값을 전달 하는 처리기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 가져올 메서드를는 **프로그램** 편집기 팩터리의 기본/기본 보기의 경우이 대화 상자.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_TextView>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` 이 값을 전달 하는 처리기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 가져올 메서드를는 **프로그램** 문서 또는 데이터 텍스트 편집기 보기에 대 한이 대화 상자.|  
|<xref:Microsoft.VisualStudio.VSConstants.LOGVIEWID_UserChooseView>|<xref:Microsoft.VisualStudio.VSConstants.GUID_VSStandardCommandSet97>`cmdidOpenWith` 이 값을 전달 하는 처리기는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUIShellOpenDocument.OpenStandardEditor%2A> 메서드를 사용 하는 사용자 정의 뷰를 선택할 수 있습니다.|  
  
## <a name="editor-factory-flags"></a>편집기 팩터리 플래그  
  
|값|설명|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_CLONEFILE>|사용 되지 않는 플래그 비트의 첫 번째 매개 변수로 결합 된 <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> 메서드.|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_OPENASNEW>|첫 번째 매개 변수로 비트 단위로 결합는 <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A>, 메서드, 나타냅니다 편집기 팩터리 문제를 해결을 수행 해야 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_OPENFILE>|첫 번째 매개 변수로 비트 단위로 결합 된 <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> 메서드를이 플래그는 함께 사용할 수의 exclusive <xref:Microsoft.VisualStudio.VSConstants.CEF_CLONEFILE>합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.CEF_SILENT>|첫 번째 매개 변수로 비트 단위로 결합는 <xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> 메서드를 나타냅니다 편집기 팩터리는 UI (사용자 인터페이스)를 표시 하지 않고 편집기를 만들어야 합니다.|  
  
## <a name="visual-studio-errors"></a>Visual Studio 오류  
  
|값|설명|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_BUSY>|비동기 동작 인터페이스에서 반환 되는 상수는 경우에 해당 개체에 이미 사용 중|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_INCOMPATIBLEDOCDATA>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] "호환 되지 않는 문서 데이터"에 대 한 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PACKAGENOTLOADED>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] "패키지를 로드 되지 않았습니다."을 나타냅니다|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTALREADYEXISTS>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 의미 하 고는 "프로젝트가 이미 있습니다."|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTMIGRATIONFAILED>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] "프로젝트를 구성 하지 못했습니다."을 나타냅니다|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_PROJECTNOTLOADED>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] "프로젝트가 로드 되지 않습니다."을 나타냅니다|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONALREADYOPEN>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 을 "솔루션 이미 열려 있습니다."를 나타냅니다|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SOLUTIONNOTOPEN>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 을 "솔루션 열려 있지 않습니다."를 나타냅니다|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_SPECIFYING_OUTPUT_UNSUPPORTED>|배열을 지정 하기 위한 매개 변수가 있는 빌드 인터페이스에 의해 반환 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsOutput> 인터페이스, 하지만 구현은 모든 출력에 메서드를만 적용할 수 있습니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_UNSUPPORTEDFORMAT>|<xref:Microsoft.VisualStudio.Package.EditorFactory.CreateEditorInstance%2A> 문서에 편집기에서 열 수 없는 형식 메서드는이 값을 반환 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_E_WIZARDBACKBUTTONPRESS>|사용자가 있는 뒤로 단추 있는지 여부를 나타내는 HRESULT 값을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 마법사.|  
  
## <a name="visual-studio-constants"></a>Visual Studio 상수  
  
|값|설명|  
|-----------|-----------------|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_PROJECTFORWARDED>|에 지정 된 HRESULT 오류가 발생 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 을 나타냅니다 "프로젝트" 전달 합니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VS_S_TBXMARKER>|에 적용 되는 상수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] "도구 상자 표식입니다."에 대 한|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_ENTERMODAL>|에 적용 되는 상수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 통해 알림 메시지를 브로드캐스트하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> 메서드 모달의 시작을 나타냅니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_EXITMODAL>|에 적용 되는 상수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 통해 알림 메시지를 브로드캐스트하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> 모달의 끝을 나타내는 방법입니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSM_TOOLBARMETRICSCHANGE>|에 적용 되는 상수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 를 통해 알림 메시지를 브로드캐스트하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBroadcastMessageEvents.OnBroadcastMessage%2A> 메서드를 나타내는 명령 모음의 메트릭을 변경 되었습니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSCOOKIE_NIL>|에 적용 되는 상수 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 쿠키 설정 되어 있지 않음을 나타내는입니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSITEMID_NIL>|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 항목의 부재를 나타내는 항목 식별자입니다. 이 값은 현재 선택 영역이 없는 경우 사용 됩니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSITEMID_ROOT>|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 항목 식별자를 프로젝트 계층의 루트를 나타내는 단일 항목이 아닌 전체 계층 구조를 확인 하는 데 사용 됩니다.|  
|<xref:Microsoft.VisualStudio.VSConstants.VSITEMID_SELECTION>|A [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 현재 선택 된 항목 또는 계층의 루트를 포함할 수 있는 항목을 나타내는 항목 식별자입니다.|  
  
## <a name="ivsselectionevents"></a>IVsSelectionEvents  
 IDE의 구성 요소가 무엇 인지 방금 선택한 경우에 설명 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSelectionEvents.OnElementValueChanged%2A> 호출 예를 들어 합니다.  
  
|상수|값|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.DocumentFrame>|0x2|  
|<xref:Microsoft.VisualStudio.VSConstants.PropertyBrowserSID>|0x4|  
|<xref:Microsoft.VisualStudio.VSConstants.StartupProject>|0x3|  
|<xref:Microsoft.VisualStudio.VSConstants.UndoManager>|0x0|  
|<xref:Microsoft.VisualStudio.VSConstants.UserContext>|0x5|  
|<xref:Microsoft.VisualStudio.VSConstants.WindowFrame>|0 x 1|  
  
## <a name="vsselelemid"></a>VSSELELEMID  
 새 선택 상태를 나타내는 데 사용 되는 상수입니다.  
  
|상수|값|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|2|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|7|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|4|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|6|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|3|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|0|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|5|  
|<xref:Microsoft.VisualStudio.VSConstants.VSSELELEMID>|1|  
  
## <a name="component-selector-dialog-constants"></a>구성 요소 선택기 대화 상수  
  
|상수|값|  
|--------------|-----------|  
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELCHANGED>|WM_USER + 1280|  
|<xref:Microsoft.VisualStudio.VSConstants.CPDN_SELDBLCLICK>|WM_USER + 1281|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_CLEARSELECTION>|WM_USER + 1290|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_GETSELECTION>|WM_USER + 1287|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZELIST>|WM_USER + 1285|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_INITIALIZETAB>|WM_USER + 1288|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_QUERYCANSELECT>|WM_USER + 1286|  
|<xref:Microsoft.VisualStudio.VSConstants.CPPM_SETMULTISELECT>|WM_USER + 1289|  
  
## <a name="see-also"></a>참고 항목  
 [프로젝트 시스템 확장을 위한 IDE 정의 명령](../extensibility/internals/ide-defined-commands-for-extending-project-systems.md)
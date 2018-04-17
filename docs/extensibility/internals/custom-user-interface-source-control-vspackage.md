---
title: 사용자 지정 사용자 인터페이스 (소스 제어 VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- user interface, source control packages
- source control packages, user interface
ms.assetid: f35ddb24-53bf-461e-b34f-7414f657c082
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: ebd2361e94e9b1430f5bac99f2e71dc53a02ebf1
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="custom-user-interface-source-control-vspackage"></a>사용자 지정 사용자 인터페이스 (소스 제어 VSPackage)
VSPackage는 Visual Studio 명령 테이블 (.vsct) 파일을 통해 해당 메뉴 항목 및 기본 상태로 선언합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) VSPackage 로드 될 때까지 기본 상태로 있는 메뉴 항목을 표시 합니다. 이후에 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드는 메뉴 항목을 사용 합니다.  
  
 명령은 사용자 인터페이스 (UI) 컨텍스트에 따라 VSPackage를 자동으로 로드 될 수 있도록 VSPackage 레지스트리 키 설정, VSPackage 방금 특정 UI 컨텍스트를 전환 하지 않고 요청 시 로드 해야 하지만 일반적으로 소스 제어 합니다. AutoLoadPackages 레지스트리 키에 대 한 자세한 내용은 참조 [관리 Vspackage](../../extensibility/managing-vspackages.md)합니다.  
  
## <a name="vspackage-ui"></a>VSPackage UI  
 소스 제어 패키지는 VSPackage로 구현 되었으며에서 UI를 사용 하지 않는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 각 소스 제어 VSPackage의 소스 제어 VSPackage에 옵션을 특정 설정에 대 한 메뉴 항목, 메뉴 그룹, 도구 창, 도구 모음 및 모든 필수 UI 같은 자체 UI 요소를 지정 해야 합니다. 이러한 UI 요소는 정적 또는 동적으로 설정할 수 있습니다. 정적 UI 요소는.vsct 파일에서 정의 하 고 VSPackage 로드 하는지 여부를 표시 됩니다. 동적 UI 요소와 같은 특정 명령 UI 컨텍스트에 따라 표시 될 수 있습니다 <xref:EnvDTE.Constants.vsContextNoSolution>, 또는에 대 한 호출의 결과로 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드. 동적 UI 요소의 표시 유형을 Vspackage의 지연된 로드에 대 한 전략을 준수합니다.  
  
## <a name="ui-constraints-on-source-control-vspackages"></a>소스 제어 Vspackage에 대 한 UI 제약 조건  
 로드 된 후 IDE에서 소스 제어 VSPackage를 제거할 수 없습니다, 때문에 VSPackage 비활성 상태가 있어야 합니다. VSPackage 활성 더 이상이 알림을 받으면 VSPackage는 UI를 사용 하지 않도록 설정 하 고 외부 IDE 상호 작용이 무시 됩니다. VSPackage 구현에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드 VSPackage를 사용 하지 않으면 명령을 숨겨야 합니다.  
  
 VSPackage 구현 해야 하는 모든 소스 제어는 `IVsSccProvider` 인터페이스입니다. 인터페이스에서 두 가지 방법 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>, VSPackage가 구현 해야 합니다.  
  
 VSPackage에서 구독에 의해 구현 되는 다양 한 IDE 이벤트에 소스 제어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>, <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>등입니다. 또한, VSPackage 수 구현한 레지스트리 사용이 가능한 콜백 인터페이스와 같은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>합니다. 이러한 모든 무시 해야 비활성 상태일 때.  
  
 다음 목록에는 소스 제어 VSPackage의 현재 상태에 따라 영향을 받는 인터페이스를 보여 줍니다.  
  
-   프로젝트 문서 이벤트를 추적 합니다.  
  
-   솔루션 이벤트입니다.  
  
-   솔루션의 지 속성 인터페이스 합니다. 비활성 상태일 때.sln 및.suo 인 파일에 패키지 작성 하지 말아야 합니다.  
  
-   Extender 속성입니다.  
  
 필요한 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, 또한 소스 제어와 관련 된 모든 선택적 인터페이스 호출 하지 않으면 소스 제어 VSPackage를 사용 하지 않으면 및 합니다.  
  
 경우는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE가 시작 되 면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage id입니다. 현재 기본 소스 제어의 ID로 명령 UI 컨텍스트를 설정 합니다. 이렇게 하면 현재 소스 제어 실제로 VSPackage를 로드 하지 않고 IDE에 표시 하기 위해 VSPackage의 정적 UI. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 등록 하는 VSPackage에 대 한 일시 중지 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통해는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider> VSPackage 호출 하기 전에.  
  
 다음 표에서 방법에 대 한 특정 세부 정보를 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 다른 UI 항목을 숨깁니다.  
  
|UI 항목|설명|  
|-------------|-----------------|  
|메뉴 및 도구 모음|소스 제어 패키지에서 원본 제어 패키지 ID를 초기 메뉴 및 도구 모음 표시 상태를 설정 해야 합니다는 [VisibilityConstraints](../../extensibility/visibilityconstraints-element.md) .vsct 파일의 섹션입니다. 이 통해는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE는 VSPackage를 로드 하 고의 구현을 호출 하지 않고 메뉴 항목의 상태를 적절 하 게 설정 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드.|  
|도구 창|소스 제어 VSPackage 비활성 만들어질 때를 소유 하 고 있는 모든 도구 창을 숨깁니다.|  
|소스 제어 VSPackage 관련 옵션 페이지|레지스트리 키 HKLM\SOFTWARE\Microsoft\VisualStudio\X.Y\ToolsOptionsPages\VisibilityCmdUIContexts 해당 옵션 페이지를 표시할 필요는 컨텍스트를 설정 하는 VSPackage를 수 있습니다. 이 키의 레지스트리 항목은 소스 제어 서비스의 ID (SID) 서비스를 사용 하 여 1의 DWORD 값을 할당 하 여 만들 수 있어야 합니다. VSPackage는 UI 이벤트가 발생할 때마다 컨텍스트에서 VSPackage 등록 된 소스 제어 활성화 된 경우 호출 됩니다.|  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>   
 <xref:EnvDTE.Constants.vsContextNoSolution>   
 [VSPackage 관리](../../extensibility/managing-vspackages.md)
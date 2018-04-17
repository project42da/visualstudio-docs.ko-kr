---
title: 관련된 서비스 및 인터페이스 (소스 제어 VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- source control packages, interfaces
- interfaces, source control packages
ms.assetid: 3e96e838-5675-46bb-99cf-40d420086038
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1f9e8e90fdda61524a9af107df452bc2b13cd90c
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="related-services-and-interfaces-source-control-vspackage"></a>관련된 서비스 및 인터페이스 (소스 제어 VSPackage)
이 섹션에서는 모든 소스 제어에서 VSPackage 관련 인터페이스는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]합니다. 소스 제어 VSPackage 이러한 인터페이스의 일부를 구현 하 고 소스 제어 작업을 수행 하기 위해 다른 사용자를 사용 합니다.  
  
## <a name="interfaces-implemented-by-and-for-source-control-vspackages"></a>소스 제어 Vspackage에 대 한 이상에 의해 구현 된 인터페이스  
 다음 인터페이스에 설명 된는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 소스 제어 VSPackage 해당 원하는 기능 집합에 따라 그 중 일부만 구현 합니다. 표시 된 일부 인터페이스 필요한로 모든 소스 제어 VSPackage가 구현 해야 합니다.  
  
 패키지를 구현 하지 않는 이러한 인터페이스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 기본 구현을 제공 합니다. 기본 구현은 없습니다 VSPackage를 등록 하는 경우 사례 없는 프로젝트에 대 한 설계는 참고 제어 됩니다. 제대로 작성 된 소스 제어 VSPackage는 해당 인터페이스의 기본 구현은을 맡기지 하지 않고 필요한 모든 인터페이스를 구현 합니다.  
  
 소스 제어 VSPackage는 다음 인터페이스의 일부 또는 전부를 캡슐화 하는 개인 서비스를 구현 해야 합니다.  
  
 인터페이스는 같습니다.  
  
-   필수: 적절 한 엔터티 (소스 제어 VSPackage, 소스 제어 스텁 project) 인터페이스를 구현 해야 합니다.  
  
-   권장: 엔터티이 인터페이스를 구현 해야이; 그렇지 않으면 소스 제어 기능 제한 될 수 있습니다.  
  
-   선택 사항: 엔터티 풍부한 기능을 제공 하려면이 인터페이스를 구현할 수 있습니다.  
  
|인터페이스|용도|에 의해 구현|구현 여부?|  
|---------------|-------------|--------------------|----------------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|편집기는 수정 하거나 파일을 저장 하기 전에이 인터페이스를 호출 합니다. 소스 제어의 VSPackage 파일을 체크 아웃 하거나 거부할 수 작업 체크 아웃이 실패 하는 경우.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|이 인터페이스를 등록 하 고 소스 제어를 사용 하 여 프로젝트를 등록 취소 하 고 기본 소스 제어 문자 모양에 대 한 지원을 제공 하는 같은 프로젝트에 기본 소스 제어 기능을 제공 합니다.|소스 제어 VSPackage|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|이 인터페이스에서 가져온는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 를 사용 하 여는 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 함수 또는 단순히 구현 하는 개체를 캐스팅 하 여 `IVsHierarchy` 를 `IVsSccProject2`합니다. 현재 소스 제어 상태 또는 위치의 프로젝트를 알리는 또는 프로젝트에서 소스 제어에서 파일 가져오기에 대 한 사용 됩니다.|프로젝트|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>|통합 모듈을 현재 활성 VSPackage를 설정 하려면이 인터페이스를 사용 합니다.|소스 제어 VSPackage|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|이 인터페이스는 구독 모델을 기반으로 합니다. 모든 VSPackage를 문서 이벤트를 받아 셸에서 수행 하려고 하는 이벤트 알림을 받을 수 브로드캐스트하며 신호를 보낼 수 있습니다. 구현 되며 처리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 다시 구현 하는 이벤트를 전달 하는 `IVsTrackProjectDocumentsEvents2` VSPackage를 합니다.|소스 제어 스텁|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3>|이 인터페이스는 일괄 처리, 동기화 된 읽기/쓰기 작업, 및는 고급 제공 `OnQueryAddFiles` 메서드.|소스 제어 스텁|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|**솔루션 탐색기** 프로젝트 파일 및 폴더 이름이 변경 되었거나 프로젝트에서 삭제 하는 경우 또는 새 파일이 프로젝트에 추가 될 때이 인터페이스를 호출 합니다. 소스 제어 VSPackage 프로젝트 파일을 체크 아웃 하거나 작업을 취소할 수 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents3>|**솔루션 탐색기** 프로젝트 IVstrackProjectDocuments3 인터페이스의 메서드에 대 한 호출에 대 한 응답에서이 인터페이스를 호출 합니다. VSPackage는 동기화 하는 일괄 처리 작업을 추적할 수 소스 제어 읽기/쓰기 작업 및 더 많은 고급 작업할 `OnQueryAddFiles` 메서드.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccEnlistmentPathTranslation>|이 인터페이스는 인 리스트 먼 트 관리 웹 프로젝트에 대 한 지원을 제공 합니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManagerTooltip>|이 인터페이스는 프로젝트의 소스 제어 파일에 대 한 도구 설명을 검색할 사용 됩니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccOpenFromSourceControl>|이 인터페이스는 네임 스페이스 확장 프로그램별 지원 기능을 제공 합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccControlNewSolution>|VSPackage이이 인터페이스를 사용 하 여 네임 스페이스 확장 프로그램을 통합 하는 **새로**, **열려**, 또는 **저장** 대화 상자. 따라서 프로젝트 자동으로 생성 시 소스 제어에 추가 하거나 추가할 수는 경우 저장 소스 제어에 작업이 적용 됩니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>|VSPackage는이 인터페이스의 노드에 대 한 소스 제어 문자 모양으로 추가 문자 모양을 정의를 사용 하 여 **솔루션 탐색기**합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccAddWebProjectFromSourceControl>|**추가** 웹 프로젝트에 대 한 대화 상자는이 인터페이스를 사용 합니다. 이전에 해당 위치에서 소스 제어 리포지토리에 추가 하는 웹 프로젝트 열기 및 소스 제어 위치에 대 한 검색을 위해 메서드를 제공 합니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>|이 인터페이스는 비동기 (백그라운드) 소스 제어에서 프로젝트에 로드에 대 한 지원을 제공합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromSccProjectEvents>|이 인터페이스에서 시작 된 비동기 로드의 진행률을 확인 하는 프로젝트에서는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>합니다.|프로젝트|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions>|이 인터페이스에서는 IDE에서이 현재 소스 제어 VSPackage를 쿼리 합니다. IDE는 VSPackage 등록 된 활성 원본 컨트롤이 없는 경우에 의미를 갖는 소스 제어 설정의 값을 쿼리 합니다. 이 인터페이스 구현 되며에 의해 처리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.|소스 제어 스텁|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>|이 인터페이스는 소스 제어 VSPackage를 등록 하는 중에 사용 됩니다.|소스 제어 스텁|필수|  
|<xref:EnvDTE.SourceControl>|이 인터페이스는 자동화에 사용 됩니다. 따라서 전용 모든 UI를 표시 하지 않고 실행 될 수 있는 기능을 노출 합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>|솔루션 (.sln) 파일에 소스 제어 설정을 저장 하려면이 인터페이스 사용 됩니다. 설정에는 소스 제어 위치 및 소스 제어 상태 플래그를 포함 합니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>|솔루션 옵션 (.suo) 파일에 소스 제어 설정을 저장 하려면이 인터페이스 사용 됩니다. 여기에 현재 사용자의 인 리스트 먼 트 위치와 같은 사용자 관련 소스 제어 설정 포함 될 수 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>|이 인터페이스는 이벤트를 모니터링 하 솔루션, 종료 또는 프로젝트를 열 때 소스 제어에서 새 파일을 가져오기 전에 프로젝트 파일에서 확인 하는 등 작업을 수행 하기 위해 사용 됩니다.|소스 제어 VSPackage|권장|  
  
## <a name="see-also"></a>참고 항목  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)
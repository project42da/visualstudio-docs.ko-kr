---
title: "관련된 서비스 및 인터페이스 (소스 제어 VSPackage) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 패키지 인터페이스"
  - "인터페이스, 소스 제어 패키지"
ms.assetid: 3e96e838-5675-46bb-99cf-40d420086038
caps.latest.revision: 26
caps.handback.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
---
# 관련된 서비스 및 인터페이스 (소스 제어 VSPackage)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 섹션에서는 모든 소스 제어 VSPackage 관련 인터페이스에 나열 되어 있는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)].  소스 제어 VSPackage 이러한 인터페이스를 구현 및 다른를 사용 하 여 소스 제어 작업을 수행 합니다.  
  
## 하 고 소스 제어 Vspackages에 대해 구현 된 인터페이스  
 다음 인터페이스에 설명 되어 있는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)], 중 일부만 해당 원하는 기능 집합에 따라 VSPackage 소스 제어를 구현 하 고 있습니다.  일부 인터페이스가 표시 된 그대로 필요 하 고 모든 소스 제어 Vspackage를 구현 해야 합니다.  
  
 패키지를 구현 하지 않는 경우 해당 인터페이스에 대 한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 의 기본 구현을 제공 합니다.  참고 기본 구현은 없습니다 Vspackage를 등록 하면 이런 하 고 프로젝트가 설계 되었는지 결정 됩니다.  제대로 작성 된 소스 제어 VSPackage 인터페이스의 기본 구현으로 유지 하는 것이 아니라 필요한 모든 인터페이스를 구현 합니다.  
  
 소스 제어 VSPackage 다음과 같은 인터페이스를 모두 또는 일부를 캡슐화 하는 개인 서비스를 구현 해야 합니다.  
  
 인터페이스는 다음과 같습니다.  
  
-   필수: 적절 한 엔티티 \(소스 제어 Vspackage를 소스 제어 스텁 프로젝트\) 인터페이스를 구현 해야 합니다.  
  
-   권장: 엔터티가이 인터페이스를 구현 해야 합니다. 그렇지 않으면 소스 제어 기능이 제한 될 수 있습니다.  
  
-   선택 사항: 엔터티 풍부한 기능을 제공 합니다이 인터페이스를 구현 합니다.  
  
|Interface|목적|관계형 데이터베이스|구현?|  
|---------------|--------|----------------|---------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>|편집자는 수정 또는 파일을 저장 하기 전에이 인터페이스를 호출 합니다.  VSPackage 소스 제어 파일을 체크 아웃 하거나 체크 아웃에 실패 하는 경우 작업을 거부할 수 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>|이 인터페이스를 등록 하 고 소스 제어에 프로젝트를 등록 취소 하 고 기본 원본 컨트롤 문자 모양에 대 한 지원을 제공 하는 것과 같은 프로젝트의 기본 소스 제어 기능 제공.|소스 제어 VSPackage|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>|이 인터페이스에서 받은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsHierarchy> 를 사용 하는 <xref:System.Runtime.InteropServices.Marshal.QueryInterface%2A> 함수를 또는 간단 하 게 구현 하는 개체를 캐스팅 하 여 `IVsHierarchy` 에 `IVsSccProject2`.  소스 제어 프로젝트에 파일을 가져오는 나 프로젝트는 현재 소스 제어 상태 또는 위치를 알리는 것에 대 한 사용 합니다.|프로젝트|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>|통합 모듈이이 인터페이스를 사용 하 여 현재 활성 Vspackage를 설정 합니다.|소스 제어 VSPackage|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>|이 인터페이스는 구독 모델을 기반으로 합니다.  문서 이벤트를 수신 하 고 셸에 의해 발생 하는 이벤트에 advise 할 려는 VSPackage 신호 수 있습니다.  구현 되 고 처리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 어떤 차례로 전달 이벤트를 구현 하는 `IVsTrackProjectDocumentsEvents2` 있는 Vspackage를.|소스 제어 스텁|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments3>|이 인터페이스를 제공 하 여 일괄 처리, 동기화 된 읽기\/쓰기 작업을 하 고가 고급 `OnQueryAddFiles` 메서드가 있습니다.|소스 제어 스텁|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents2>|**솔루션 탐색기** 프로젝트는 프로젝트에 새 파일을 추가 하거나 파일 및 폴더 이름을 변경 하거나 프로젝트에서 삭제 하는 경우이 인터페이스를 호출 합니다.  소스 제어 VSPackage 프로젝트 파일을 체크 아웃 하거나 작업을 취소할 수 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocumentsEvents3>|**솔루션 탐색기** 프로젝트에 응답 IVstrackProjectDocuments3 인터페이스의 메서드를 호출 하 여이 인터페이스를 호출 합니다.  VSPackage 동기화 하는 일괄 처리 된 작업을 추적할 수 있는 소스 제어 읽기\/쓰기 작업을 하는 고급 함께 작동 `OnQueryAddFiles` 메서드가 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccEnlistmentPathTranslation>|인 리스트 먼 트 관리를 지 원하는 웹 프로젝트의 경우이 인터페이스를 제공 합니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManagerTooltip>|이 인터페이스를 사용 하 여 프로젝트의 소스 제어 파일에 대 한 도구 설명을 검색할 수 있습니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccOpenFromSourceControl>|이 인터페이스는 네임 스페이스 확장 지원을 제공합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccControlNewSolution>|Vspackage를이 인터페이스를 사용 하 여 네임 스페이스 확장으로 통합 하는  **New**,  **열기**, 또는  **저장** 대화 상자.  따라서 프로젝트 수 있습니다 자동으로 소스 컨트롤을 작성, 추가 또는 저장 하는 경우 소스 제어에 추가 작업이 적용 됩니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccGlyphs>|있는 Vspackage이이 인터페이스를 사용 하 여 단어로 원본 컨트롤의 노드에 대 한 추가 문자 모양을 정의  **솔루션 탐색기**.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccAddWebProjectFromSourceControl>|해당  **추가** 이 인터페이스를 사용 하 여 웹 프로젝트의 대화 상자입니다.  및 소스 제어 저장소에서 그 위치에 이전에 추가 웹 프로젝트를 열거나 소스 제어 위치에 대 한 검색을 위한 메서드를 제공 합니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>|이 인터페이스 비동기 \(백그라운드\) 로드 프로젝트에서 소스 제어를 지원합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromSccProjectEvents>|이 인터페이스는 프로젝트 진행 상황에 의해 시작 된 비동기 로딩을 볼 수 있습니다 <xref:Microsoft.VisualStudio.Shell.Interop.IVsAsynchOpenFromScc>.|프로젝트|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSccToolsOptions>|이 인터페이스에는 IDE에 현재 소스 제어 Vspackage를 쿼리할 수 있습니다.  IDE VSPackage 등록 없이 현재 원본 컨트롤 경우에 의미를 갖게 하는 소스 제어 설정의 값을 쿼리 합니다.  이 인터페이스를 구현 하 고 처리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].|소스 제어 스텁|필수|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsRegisterScciProvider>|소스 제어 Vspackage를 등록 하는이 인터페이스를 사용 합니다.|소스 제어 스텁|필수|  
|<xref:EnvDTE.SourceControl>|이 인터페이스는 자동화에 사용 됩니다.  따라서, 모든 UI를 표시 하지 않고 실행 될 수 있는 함수에만 노출 합니다.|소스 제어 VSPackage|Optional|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionProps>|이 인터페이스를 사용 하 여 소스 제어 설정을 솔루션 \(.sln\) 파일에 저장 합니다.  소스 제어 위치와 소스 제어 상태 플래그가 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsPersistSolutionOpts>|이 인터페이스를 사용 하 여 소스 제어 설정의 솔루션 옵션 파일 \(.suo\)에 저장 합니다.  이 현재 사용자의 참여가 위치와 같은 사용자 특정 소스 제어 설정을 포함할 수 있습니다.|소스 제어 VSPackage|권장|  
|<xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>|이 인터페이스 이벤트를 모니터링 하려면 솔루션 닫기 또는 프로젝트를 열 때 소스 제어에서 새 파일을 가져오기 전에 프로젝트 파일을 검사 하는 등의 작업을 수행 하기 위해 사용 됩니다.|소스 제어 VSPackage|권장|  
  
## 참고 항목  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)
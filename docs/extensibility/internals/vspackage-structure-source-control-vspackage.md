---
title: "VSPackage 구조 (소스 제어 VSPackage) | Microsoft Docs"
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
  - "Vspackage를 구조"
  - "소스 제어 패키지 VSPackage 개요"
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
caps.latest.revision: 26
caps.handback.revision: 26
ms.author: "gregvanl"
manager: "ghogen"
---
# VSPackage 구조 (소스 제어 VSPackage)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 패키지 SDK는 VSPackage를 만들기 위한 지침 허용 된 자신의 소스 제어 기능을 통합 하는 소스 제어 구현자는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경입니다. VSPackage는 일반적으로 하 여 요청 시 로드 되는 COM 구성 요소는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 레지스트리 항목의 패키지에서 보급 된 서비스를 기반으로 통합된 개발 환경 \(IDE\). 모든 VSPackage를 구현 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>합니다. VSPackage에서 제공 하는 서비스를 일반적으로 사용 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE 자체의 일부 서비스 proffers 및입니다.  
  
 VSPackage 해당 메뉴 항목을 선언 하 고.vsct 파일을 통해 기본 항목 상태를 설정 합니다.[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE VSPackage가 로드 될 때까지이 상태에 메뉴 항목을 표시 합니다. 그 이후에, VSPackage의 구현에서 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드는 메뉴 항목을 사용할지 여부를 합니다.  
  
## 소스 제어 패키지 특성  
 VSPackage에 강력 하 게 통합 되는 소스 제어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 VSPackage 의미 체계는 다음과 같습니다.  
  
-   VSPackage 있기 때문에 구현 될 인터페이스 \(의 `IVsPackage` 인터페이스\)  
  
-   UI 명령 구현 \(.vsct 파일 및 구현의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스\)  
  
-   등록 된 VSPackage의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 소스 제어 VSPackage와 통신 해야 이러한 다른 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 엔터티:  
  
-   프로젝트  
  
-   편집기  
  
-   솔루션  
  
-   Windows  
  
-   실행 중인 document 테이블  
  
### 사용 될 수 있는 visual Studio 환경 서비스  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 SVsRegisterScciProvider 서비스  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>  
  
### VSIP 인터페이스 구현 및 호출  
 소스 제어 패키지 VSPackage 이며 등록 된 다른 Vspackage 직접 상호 작용할 수 따라서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 전체 범위의 소스 제어 기능을 제공 하기 위해 소스 제어 VSPackage 처리할 수 프로젝트 또는 셸에서 제공 하는 인터페이스입니다.  
  
 모든 프로젝트 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구현 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> 내에서 프로젝트로 인식 되는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE입니다. 그러나이 인터페이스는 특수화 된 하지 소스 제어에 대해 충분 합니다. 원본에서 할 수 있어야 하는 프로젝트 제어 구현에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>합니다. 이 인터페이스는 해당 내용에 대 한 프로젝트를 쿼리 하 고 문자 모양 및 바인딩 정보 \(서버 위치 및 소스 제어 되는 프로젝트의 디스크 위치 사이의 연결을 설정 하는 데 필요한 정보\) 제공 VSPackage 소스 제어에서 사용 됩니다.  
  
 VSPackage를 구현 하는 소스 제어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>, 를 하 고이 통해 프로젝트를 소스 제어에 대 한 등록 되며 해당 상태 문자를 검색 합니다.  
  
 소스 제어 VSPackage를 고려해 야 하는 인터페이스의 전체 목록은 참조 하십시오. [관련된 서비스 및 인터페이스](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)합니다.  
  
## 참고 항목  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)   
 [관련된 서비스 및 인터페이스](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)
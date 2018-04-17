---
title: VSPackage 구조 (소스 제어 VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- VSPackages, structure
- source control packages, VSPackage overview
ms.assetid: 92722be7-b397-48c3-a7a7-0b931a341961
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 13b811b504259bf10440419b3cb4029a4c239c5e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="vspackage-structure-source-control-vspackage"></a>VSPackage 구조 (소스 제어 VSPackage)
원본 제어 패키지 SDK는 자신의 소스 제어 기능을 통합 하는 소스 제어 구현자를 허용 하는 VSPackage를 만들기 위한 지침을 제공 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경입니다. VSPackage는 COM 구성 요소에 의해 요청 시 일반적으로 로드 되는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 레지스트리 항목에서 패키지를 통해 보급 된 서비스를 기반으로 한 통합된 개발 환경 (IDE). 모든 VSPackage를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>합니다. 제공 하는 서비스를 일반적으로 사용 하는 VSPackage는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE proffers 자체의 일부 서비스 및 합니다.  
  
 VSPackage는 해당 메뉴 항목을 선언 하 고.vsct 파일을 통해 기본 항목 상태를 설정 합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE는 VSPackage 로드 될 때까지이 상태로 메뉴 항목을 표시 합니다. 그 후 VSPackage 구현에서의 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget.QueryStatus%2A> 메서드는 메뉴 항목을 사용 합니다.  
  
## <a name="source-control-package-characteristics"></a>원본 제어 패키지 특성  
 VSPackage는를 깊이 있게 통합 소스 제어 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 VSPackage 의미 체계는 다음과 같습니다.  
  
-   VSPackage 있기 때문에 구현 될 인터페이스 (의 `IVsPackage` 인터페이스)  
  
-   UI 명령을 구현 (.vsct 파일의 및 구현은 <xref:Microsoft.VisualStudio.OLE.Interop.IOleCommandTarget> 인터페이스)  
  
-   등록 된 VSPackage의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 소스 제어 VSPackage와 통신 해야 이러한 다른 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 엔터티:  
  
-   프로젝트  
  
-   편집기  
  
-   솔루션  
  
-   Windows  
  
-   실행 중인 문서 테이블  
  
### <a name="visual-studio-environment-services-that-may-be-consumed"></a>사용 될 수 있는 visual Studio 환경 서비스  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>  
  
 SVsRegisterScciProvider 서비스  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsTrackProjectDocuments>  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.SVsSccManager>  
  
### <a name="vsip-interfaces-implemented-and-called"></a>VSIP 인터페이스 구현 및 호출  
 원본 제어 패키지는 VSPackage 및 등록 된 다른 Vspackage와 직접 상호 작용할 수 따라서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 전체 범위의 소스 제어 기능을 제공 하기 위해 소스 제어 VSPackage로 처리할 수 있는 프로젝트 또는 셸에서 제공 하는 인터페이스입니다.  
  
 모든 프로젝트 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProject3> 내의로 인식 되는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE. 그러나이 인터페이스는 특수화 된 하지 소스 제어에 대해 충분 합니다. 소스에서 사용 중인 것으로 예상 되는 프로젝트 제어 구현은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProject2>합니다. 이 인터페이스는 해당 내용에 대 한 프로젝트를 쿼리 하 고 문자 모양과 (정보 서버 위치 및 아래에 있는 프로젝트의 디스크 위치 사이의 연결을 설정 하는 데 필요한 바인딩 정보를 제공 VSPackage 소스 제어에서 사용 됩니다. 소스 제어)입니다.  
  
 VSPackage 구현 소스 제어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccManager2>를 차례로 프로젝트는 소스 제어에 대 한 등록 되며 해당 상태 문자를 검색할 수 있습니다.  
  
 소스 제어 VSPackage를 고려해 야 하는 인터페이스의 전체 목록은 참조 하십시오. [관련 서비스 및 인터페이스](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디자인 요소](../../extensibility/internals/source-control-vspackage-design-elements.md)   
 [관련된 서비스 및 인터페이스](../../extensibility/internals/related-services-and-interfaces-source-control-vspackage.md)
---
title: "소스 제어의 새로운 기능 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "새 [Visual Studio SDK], 소스 컨트롤 이란"
  - "새로운 소스 제어 [Visual Studio SDK]"
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
caps.latest.revision: 27
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 27
---
# 소스 제어의 새로운 기능
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] VSPackage 소스 컨트롤을 구현 하 여 밀접 하 게 통합된 된 소스 제어 솔루션을 제공할 수 있습니다.  이 섹션에서는 VSPackages 소스 컨트롤의 기능을 설명 및 개요를 구현 하는 단계를 제공 합니다.  
  
## 소스 제어 VSPackage  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]소스 제어 솔루션의 두 가지 유형을 지원합니다.  모든 버전의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 여전히 소스 제어 플러그 인 API 기반 통합 하 여 플러그 인.  깊은 통합을 제공 하는 소스 제어에 있는 Vspackage를 만들 수도 있습니다 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 높은 수준의 세련미와 자율성을 요구 하는 소스 제어 솔루션에 대 한 적절 한 경로입니다.  
  
 있는 VSPackage 거의 모든 종류의 기능을 추가할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  소스 제어 VSPackage 제공 완전 한 소스 제어 기능에 대 한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 사용자의 백 엔드 통신 소스 제어 시스템을 제공 하는 UI에서.  
  
 소스 제어 Vspackage를 구현 하는 "모두 또는 아무것도" 전략이 필요 합니다.  소스 제어 VSPackage 만든 상당한 여러 소스 컨트롤 인터페이스를 구현 하는 노력을 투자 해야 하 고 새로운 UI 요소 \(대화 상자, 메뉴 및 도구 모음\)에 전체 소스 제어 기능으로 패키지를 성공적으로 통합 하는 데 필요한 인터페이스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 일반 개요는 소스 제어 패키지를 구현 하는 데 필요한의 다음 단계를 제공 합니다.  자세한 내용은 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)를 참조하십시오.  
  
1.  전용 소스 제어 서비스 proffers은 Vspackage를 만듭니다.  
  
2.  인터페이스에 의해 proffered 되는 소스 제어와 관련 된 서비스 구현 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] \(예를 들어,는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> 인터페이스\).  
  
3.  소스 제어 Vspackage를 등록 합니다.  
  
4.  모든 소스 제어 항목 메뉴, 대화 상자, 도구 모음 및 상황에 맞는 메뉴를 포함 하 여 UI를 구현 합니다.  
  
5.  활성 상태 이므로 하면 Vspackage가 처리 해야 할 때 모든 소스 제어와 관련 된 이벤트 Vsackage를 소스 제어에 전달 됩니다.  
  
6.  VSPackage 소스 제어 해야 듣는 것과 같은 이벤트에 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> 트랙 프로젝트 문서 \(TPD\) 이벤트 인터페이스 \(구현으로 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 인터페이스\) 다음 필요한 조치를 취합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [개요](../../extensibility/internals/source-control-integration-overview.md)   
 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)
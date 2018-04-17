---
title: 어떤&#39;소스 제어의 새로운 s | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- what's new [Visual Studio SDK], source control
- source control [Visual Studio SDK], what's new
ms.assetid: bcf85418-18fb-4824-9dae-d14bf3d56a77
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: b46730ab1acac6605af2e1ff1c418dbe8c886406
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="what39s-new-in-source-control"></a>어떤&#39;s 소스 제어의 새로운
[!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 소스 제어 VSPackage를 구현 하 여 밀접 하 게 통합된 소스 제어 솔루션을 제공할 수 있습니다. 이 섹션 소스 제어 Vspackage의 기능을 설명 하 고 구현 하는 단계에 대해 간략하게 설명 합니다.  
  
## <a name="the-source-control-vspackage"></a>소스 제어 VSPackage  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 두 가지 유형의 원본 제어 솔루션을 지원합니다. 모든 버전의에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 소스 제어 플러그 인 API 기반 통합할 수도 있습니다 플러그 인 합니다. 전체 통합을 제공 하는 소스 제어에 대 한 VSPackage를 만들 수도 있습니다 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 높은 수준의 지원 및 자치를 필요로 하는 원본 제어 솔루션에 적합 한 경로입니다.  
  
 VSPackage는 거의 모든 종류의 기능을 추가할 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 소스 제어 VSPackage에 대 한 완전 한 소스 제어 기능을 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 소스 제어 시스템과 백 엔드 통신을 사용자에 게 UI에서 합니다.  
  
 소스 제어 VSPackage를 구현 하는 "전체 또는 아무 것 도" 전략이 필요 합니다. 소스 제어 VSPackage의 작성자 해야 하는 데 투자 상당한 노력을 다양 한 소스 제어 인터페이스와 새 UI 요소 (대화 상자, 메뉴 및 도구 모음) 전체 소스 제어 기능을 포괄 하도록 구현 인터페이스 및 성공적으로 통합 하는 데 필요한 모든 패키지의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 다음 단계는 원본 제어 패키지를 구현 하는 데 필요한 일반적인 개요를 제공 합니다. 자세한 내용은 참조 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)합니다.  
  
1.  개인 소스 제어 서비스 proffers 하는 VSPackage를 만듭니다.  
  
2.  제공 하는 소스 제어와 관련 된 서비스에서 인터페이스를 구현 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (예를 들어는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider> 인터페이스).  
  
3.  소스 제어 VSPackage를 등록 합니다.  
  
4.  모든 소스 제어 메뉴 항목과 대화 상자, 도구 모음, 상황에 맞는 메뉴를 포함 하 여 UI를 구현 합니다.  
  
5.  활성화 하 고 VSPackage에서 처리 되어야 하는 경우 모든 소스 제어와 관련 된 이벤트 소스 제어 VSackage에 전달 됩니다.  
  
6.  소스 제어 VSPackage 구현 하는 것 등의 이벤트를 수신 해야는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3> 트랙 프로젝트 문서 TPD () 이벤트 뿐만 아니라 인터페이스 (여 구현 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2> 인터페이스) 하 고 필요한 조치를 수행 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsQueryEditQuerySave2>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3>   
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsTrackProjectDocuments2>   
 [개요](../../extensibility/internals/source-control-integration-overview.md)   
 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)
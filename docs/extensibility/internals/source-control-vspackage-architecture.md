---
title: "소스 제어 VSPackage 아키텍처 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어 패키지, 아키텍처"
ms.assetid: 453125fc-23dc-49b1-8476-94581f05e6c7
caps.latest.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 25
---
# 소스 제어 VSPackage 아키텍처
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스 제어 패키지를 사용 하 여 VSPackage 서비스가 되는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE를 제공 합니다.  소스 제어 패키지는 소스 제어 서비스 기능을 제공 합니다.  또한 소스 제어 패키지는 소스 제어에 통합 하는 플러그 인 보다는 더 다재 다능 한 대체 됩니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 엄격한 계약에는 소스 제어 플러그 인 API를 구현 하는 플러그 인을 abides.  예를 들어, 플러그인의 기본 대체할 수 없습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자 인터페이스 \(UI\)입니다.  또한, 소스 제어 플러그 인 API 자체 소스 제어 모델을 구현 하는 플러그 인 사용 하지 않습니다.  그러나 소스 제어 패키지를 이러한 한계를 모두 극복.  소스 제어 패키지는 소스 제어 경험을 통해 완벽 한 제어 되어 있는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자입니다.  또한 소스 제어 패키지는 자체 소스 제어 모델 및 논리를 사용할 수 있습니다 및 모든 소스 제어와 관련 된 사용자 인터페이스를 정의할 수 있습니다.  
  
## 소스 제어 패키지 구성 요소  
 아키텍처 다이어그램에 표시 된 대로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 라는 소스 제어 스텁 구성 요소는 소스 제어 패키지에 통합 되어 있는 VSPackage [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 소스 제어 스텁 다음과 같은 작업을 처리합니다.  
  
-   소스 제어 패키지 등록에 필요한 공통 UI를 제공 합니다.  
  
-   소스 제어 패키지를 로드합니다.  
  
-   소스 제어 패키지를 활성\/비활성으로 설정합니다.  
  
 소스 제어 스텁 활성 서비스 소스 제어 패키지를 찾아 들어오는 모든 서비스 호출 IDE에서 해당 패키지를 라우팅합니다.  
  
 특별 한 소스 제어 패키지는 소스 제어 어댑터 패키지는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 제공 합니다.  이 패키지에 소스 제어 플러그 인 API에 따라 소스 제어 플러그 인을 지원의 핵심 구성 요소입니다.  플러그 인 플러그 인 활성화 되 면 소스 제어 스텁 해당 이벤트 소스 컨트롤 어댑터 패키지를 보냅니다.  결과적으로 어댑터 소스 제어 패키지 소스 제어 플러그 인에서 소스 제어 플러그 인 API를 사용 하 여 통신 및 또한 기본은 모든 소스 제어 플러그 인에 대 한 공통 UI를 제공 합니다.  
  
 현재 패키지는 소스 제어 패키지는 때 반면, 소스 제어 스텁 직접 패키지를 사용 하 여 통신의 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 소스 제어 패키지를 인터페이스입니다.  소스 제어 패키지를 호스팅 자체 소스 제어 UI에 대 한 책임이 있습니다.  
  
 ![소스 컨트롤 아키텍처 그래픽](~/extensibility/internals/media/vsipsccarch.gif "VSIPSCCArch")  
  
 소스 제어 패키지, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 코드 또는 통합을 위한 API를 제공 하지 않습니다.  이에 설명 된 방법을 사용 대비 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md) 소스 제어 플러그 인 있는 강성 세트 하 고 콜백 함수를 구현 합니다.  
  
 모든 Vspackage와 같은 소스 제어 패키지는 COM 개체를 사용 하 여 만들 수 있습니다입니다 `CoCreateInstance`.  있는 Vspackage은 사용할 수 있습니다의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 을 구현 하 여 IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>.  인스턴스를 만들 때 사이트 포인터는 Vspackage를 수신 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> VSPackage 액세스는 사용할 수 있는 서비스와 ide에서 인터페이스를 제공 하는 인터페이스입니다.  
  
 소스 제어 플러그 인 API 기반 쓰기 보다 고급 프로그래밍 전문 지식이 필요 VSPackage 기반 소스 제어 패키지를 작성 플러그 인입니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 [시작](../../extensibility/internals/getting-started-with-source-control-vspackages.md)
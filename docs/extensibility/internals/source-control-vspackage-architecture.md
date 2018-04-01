---
title: 원본 제어 VSPackage 아키텍처 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- source control packages, architecture
ms.assetid: 453125fc-23dc-49b1-8476-94581f05e6c7
caps.latest.revision: 25
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 002dea54b63a78975d56464319614d369a9b2318
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="source-control-vspackage-architecture"></a>소스 제어 VSPackage 아키텍처
소스 제어 패키지 되는 서비스를 사용 하는 VSPackage는는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE를 제공 합니다. 소스 제어 패키지는 원본 제어 서비스와 해당 기능을 제공합니다. 또한, 소스 제어 패키지는 원본 제어 플러그 인에 소스 제어 통합을 보다 더 융통성 대체 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 소스 제어 플러그 인 소스 제어 플러그 인 API를 구현 하는 엄격한 계약에 따라 관련 합니다. 예를 들어 플러그 인 바꿀 수 없습니다 기본 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] UI (사용자 인터페이스). 또한, 소스 제어 플러그 인 API 자체의 소스 제어 모델을 구현 하는 플러그 인을 사용 하지 않습니다. 그러나 원본 제어 패키지 모두 이러한 한계를 극복합니다. 원본 제어 환경 완전히 제어를 포함 하는 패키지에 소스 제어는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자입니다. 또한 소스 제어 패키지 자체의 소스 제어 모델 및 논리를 사용할 수 있고 모든 소스 제어 관련 사용자 인터페이스를 정의할 수 있습니다.  
  
## <a name="source-control-package-components"></a>소스 제어 패키지 구성 요소  
 아키텍처 다이어그램에 나와 있는 것 처럼는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 스텁 라는 구성 요소가 사용 하 여 원본 제어 패키지를 통합 하는 VSPackage는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 소스 제어 스텁 다음 작업을 처리합니다.  
  
-   소스 제어 패키지 등록에 필요한 일반적인 UI를 제공 합니다.  
  
-   소스 제어 패키지를 로드합니다.  
  
-   활성/비활성으로 원본 제어 패키지를 설정합니다.  
  
 소스 제어 스텁 소스 제어 패키지에 대 한 활성 서비스 찾은 IDE에서 들어오는 모든 서비스 호출 하는 패키지에 라우팅합니다.  
  
 소스 제어 어댑터 패키지는 특수 한 소스 제어 패키지는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 를 제공 합니다. 이 패키지는 소스 제어 플러그 인 API에 따라 소스 제어 플러그 인을 지원 하기 위한 주요 구성 요소입니다. 플러그 인 활성 소스 제어 플러그 인을 사용 하는 경우 소스 제어 스텁 소스 제어 어댑터 패키지를 해당 이벤트를 보냅니다. 차례로 소스 제어 어댑터 패키지 소스 제어 플러그 인 API를 사용 하 여 소스 제어 플러그 인와 통신 하 고 기본 모든 소스 제어 플러그 인에 대 한 공통 되는 UI를 제공 합니다.  
  
 소스 제어 패키지 활성 패키지 이면 반면에 소스 제어 스텁 직접 통신 하는 패키지를 사용 하 여는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 원본 제어 패키지 인터페이스입니다. 소스 제어 패키지는 소스 제어 UI는 자체 호스팅 담당 합니다.  
  
 ![소스 제어 아키텍처 그래픽](../../extensibility/internals/media/vsipsccarch.gif "VSIPSCCArch")  
  
 소스 제어 패키지에 대 한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 소스 제어 코드 또는 통합에 대 한 API를 제공 하지 않습니다. 에 설명 된 접근 방식으로 이와 반대로 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md) 함수와 콜백을의 고정 된 관계로 집합을 구현 하도록 소스 제어 플러그 인에 있는 합니다.  
  
 모든 VSPackage와 같은 원본 제어 패키지는 COM 개체를 사용 하 여 만들 수 있는 `CoCreateInstance`합니다. VSPackage은 사용할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 구현 하 여 IDE <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>합니다. VSPackage 사이트 포인터를 받는 인스턴스를 만들 때와 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider> VSPackage 액세스는 사용 가능한 서비스 및 IDE에서 인터페이스를 제공 하는 인터페이스입니다.  
  
 소스 제어 플러그 인 API 기반 쓰는 것 보다 더 많은 고급 프로그래밍 전문 지식이 필요 소스 제어 VSPackage를 기반으로 패키지 작성 플러그 인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsPackage>   
 [시작](../../extensibility/internals/getting-started-with-source-control-vspackages.md)
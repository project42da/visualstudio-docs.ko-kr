---
title: "소스 제어 통합 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: source control [Visual Studio SDK], about source control
ms.assetid: 3a46e4eb-e677-49c3-8647-d927d035a19a
caps.latest.revision: "16"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: ed0ffd44e248cb1f420cb7be308a46c914fffee2
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="source-control-integration-overview"></a>소스 제어 통합 개요
이 단원에는 Visual Studio 소스 제어;에 통합 하는 두 가지 방법을 비교합니다 소스 제어 플러그 인 및 원본 제어 솔루션을 제공 하 고 새 소스 제어 기능을 강조 표시 하는 VSPackage입니다. Visual Studio 솔루션을 기반으로 자동 전환 뿐 아니라 소스 제어 Vspackage 및 소스 제어 플러그 인 간 수동 전환 수 있습니다.  
  
## <a name="source-control-integration"></a>소스 제어 통합  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]두 가지 유형의 소스 제어 통합 옵션을 지원합니다. 모든 버전의에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]를 통합할 수도 있습니다 API에 따라 소스 제어 플러그 인 (이전에 라고도 MSSCCI API)를 소스 제어 사용자 인터페이스 (Visual Studio를 사용 하는 동안 기본 소스 제어 기능을 제공 하는 플러그 인 UI)입니다. 소스 제어 VSPackage, 반면에 새로 만들었거나, 딥 통합을 제공 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 높은 수준의 지원 및의 소스 제어 모델에는 자치를 요구 하는 소스 제어 통합에 대 한 적절 한 경로입니다.  
  
 ![소스 제어 개요](../../extensibility/internals/media/sourcectnrloverview.gif "SourceCtnrlOverview")  
  
## <a name="source-control-plug-in"></a>소스 제어 플러그 인  
 모든 버전의 Visual Studio 통합 경로로 소스 제어 플러그 인 API 사양 버전 1.2 지원 합니다. 소스 제어 플러그 인 구현자에 설명 된 대로 소스 제어 통합 및 등록에 대 한 소스 제어 플러그 인 API 함수를 구현 하는 DLL 작성 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)합니다. 이 방법에서는 통합 개발 환경 (IDE) 사용 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 체크 인, 체크 아웃, 도구/옵션 속성 페이지, 도구 모음 및 소스 제어 문자 같은 대화 상자에 대 한 UI입니다. 엄격한 준수 소스 제어 플러그 인 API를 사용 하면 Visual Studio 및 사용자에 대 한 문제 없이 환경에 쉽게 통합 합니다. 즉, 소스 제어 플러그 인에 대부분의 함수 및 API에 자세히 설명 하는 콜백을 구현 해야 합니다.  
  
 소스 제어 플러그 인 API를 사용 하 여 플러그 인 소스 제어를 구현 하려면 다음이 단계를 따르십시오.  
  
1.  에 지정 된 함수를 구현 하는 DLL을 만드는 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md)합니다.  
  
2.  적절 한 레지스트리 항목을 만들어서 DLL을 등록 (에 설명 된 [하는 방법: 소스 제어 플러그 인 설치](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)).  
  
3.  UI 및 표시 (Visual Studio 구성 요소 소스 제어 플러그 인을 통해 소스 제어 기능을 처리 하는) 소스 제어 어댑터 패키지에서 메시지를 표시 하는 도우미 만들기  
  
 소스 제어 명령에 대 한 응답으로 Visual Studio IDE 기본 작업에 대 한 표준 UI를 표시 한 다음 정보를 전달 소스 제어 플러그 인 소스 제어 플러그 인 API에 정의 된 함수를 통해 합니다. 고급 옵션에 대 한 소스 제어 플러그 인에 호출할 수는 자체 UI를 표시 하도록 예를 들어 소스 제어 프로젝트에 대 한 검색 합니다. 즉, 사용자 소스 제어를 처리할 때 UI의 두 개의 서로 다른 스타일으로 표시 될 수 있습니다: Visual Studio에서는 표시 하는 UI 및 UI를 소스 제어 플러그 인을 제공 합니다. 이 고급 소스 제어 작업에서 가장 크게 나타납니다.  
  
### <a name="drawbacks-to-implementing-a-source-control-plug-in"></a>소스 제어 플러그 인을 구현 하는 데 단점  
  
-   고급 기능에 대 한는 표시 되지만 인터페이스의 두 가지 스타일 혼동 하 합니다.  
  
-   소스 제어 플러그 인이 소스 제어 플러그 인 API 사용 권한에 포함 된 소스 제어 모델에만 적용 됩니다.  
  
-   소스 제어 플러그 인 API는 일부 소스 제어 시나리오에 대 한 너무 제한적일 수 있습니다.  
  
### <a name="advantages-to-implementing-a-source-control-plug-in"></a>소스 제어 플러그 인을 구현 하는 이점  
  
-   Visual Studio에서 소스 제어 플러그 인 잠재적으로 복잡 한 UI를 구현 하지 않아도 되도록 모든 기본 소스 제어 작업에 대 한 모든 UI를 제공 합니다.  
  
-   엄격한 API 때문에 소스 제어 플러그 인 쉽게 상호 작용할 수; 보다 광범위 한 기능을 제공 하는 외부 소스 제어 프로그램 Visual Studio 영향을 받지 않으며 훨씬 어떻게 너무 소스 제어 기능을 달성 하는 소스 제어 플러그 인 API에 따라 수행 됩니다.  
  
-   VSPackage는 소스 제어 플러그 인 소스 제어를 구현 하는 것이 쉽습니다.  
  
## <a name="source-control-vspackage"></a>소스 제어 VSPackage  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]소스 제어 기능에 대 한 모든 제어 및 Visual Studio에서 제공 하는 소스 제어 사용자 인터페이스의 완전 한 대체와 Visual Studio에 완벽 한 통합을 허용합니다. 소스 제어 VSPackage Visual Studio에 등록 하 고 소스 제어 기능을 제공 합니다. Visual Studio와 함께 여러 가지 소스 제어 Vspackage를 등록 수, 둘 중 하나만 활성화할 수 한 번에 있습니다. 소스 제어 VSPackage는 활성화 되어 있는 동안 소스 제어 기능 및 모양에 대 한 모든 권한을 Visual Studio에서에 있습니다. 다른 모든 소스 제어 시스템에 등록 될 수 있는 Vspackage 활성화 되며 모든 UI를 전혀 표시 되지 않습니다.  
  
 소스 제어 VSPackage를 구현 하는 "전체 또는 아무 것 도" 전략이 필요 합니다. 소스 제어 VSPackage의 작성자에 상당한 노력을 구현 하는 다양 한 소스 제어 인터페이스와 새 UI 요소 (대화 상자, 메뉴 및 도구 모음) 전체 소스 제어 기능을 포괄 하도록 투자 해야 합니다. 참조 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md) 내용을 확인 합니다.  
  
### <a name="drawbacks-to-implementing-a-source-control-vspackage"></a>소스 제어 VSPackage를 구현 하는 데 단점  
  
-   VSPackage는 다양 한 Visual Studio와 함께 성공적으로 통합 하는 복잡 한 인터페이스를 구현 해야 합니다.  
  
-   VSPackage; 소스 제어에 필요한 모든 UI를 제공 해야 합니다. Visual Studio는이 영역에 도움을 제공 합니다.  
  
-   소스 제어 VSPackage 깊이 Visual Studio에 연결 된 하 고 있으므로 소스 제어 프로그램의 외부 버전와 기능을 쉽게 공유할 수 없는 독립 실행형 프로그램으로 작업할 수 없습니다.  
  
### <a name="advantages-to-implementing-a-source-control-vspackage"></a>소스 제어 VSPackage를 구현 하는 이점  
  
-   소스 제어 UI에 대 한 모든 권한 및 기능에는 VSPackage에 있으므로 사용자가 소스 제어에 대 한 원활한 인터페이스가 표시 됩니다.  
  
-   VSPackage는 특정 소스 제어 모델으로 제한 되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [소스 제어](../../extensibility/internals/source-control.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)   
 [소스 제어의 새로운 기능](../../extensibility/internals/what-s-new-in-source-control.md)
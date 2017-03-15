---
title: "소스 제어 통합 개요 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "소스 제어에 대 한 소스 제어 [Visual Studio SDK]"
ms.assetid: 3a46e4eb-e677-49c3-8647-d927d035a19a
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# 소스 제어 통합 개요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 단원에서는 Visual Studio 소스 제어로 통합 하는 데는 두 가지 방법으로 비교 합니다. 소스 제어 플러그 인 및 소스 제어 솔루션을 제공 하 고 새로운 소스 제어 기능을 강조 VSPackage.  Visual Studio 수동 VSPackages 소스 제어와 소스 제어 플러그 인 간의 전환 뿐 아니라에 자동 스위칭 솔루션을 기반으로 수 있습니다.  
  
## 소스 제어 통합  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]소스 제어 통합 옵션 두 가지를 지원합니다.  모든 버전의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 여전히 플러그 인에서 소스 제어 플러그 인 \(이전에 MSSCCI API로 라고도 함\), Visual Studio 소스 제어 사용자 인터페이스 \(UI\)를 사용 하는 동안 기본 소스 제어 기능을 제공 하는 API 기반으로 통합할 수 있습니다.  소스 제어 VSPackage, 반면, 새, 깊은 통합을 제공 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 경로 높은 수준의 세련미와 자율성의 소스 제어 모델에서 요청 하는 소스 제어 통합에 적합 합니다.  
  
 ![소스 제어 개요](../../extensibility/internals/media/sourcectnrloverview.png "SourceCtnrlOverview")  
  
## 소스 제어 플러그 인  
 Visual Studio 모든 버전이 소스 제어 플러그 인 API 사양 버전 1.2 통합 경로 지원합니다.  소스 제어 플러그 인 구현에서 설명 하는 대로 소스 제어 통합 및 등록에 대 한 소스 제어 플러그 인 API 함수를 구현 하는 DLL 씁니다 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md).  통합 개발 환경 \(IDE\)이 접근이 방식에서 사용 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 체크 인, 체크 아웃, 도구\/옵션 속성 페이지, 도구 모음 및 소스 제어 문자 모양을 같은 대화 상자에 대 한 UI입니다.  엄격 하 게 유지 하는 소스 제어 플러그 인 API는 Visual Studio 하 고, 사용자는 문제 없이 입장에 쉽게 통합 산정.  따라서 대부분의 기능 및 API에 자세히 설명 된 콜백 소스 제어 플러그 인을 구현 해야 합니다.  
  
 소스 제어 플러그 인 API를 사용 하 여 플러그 인을 구현 하려면 다음과 같이 하십시오.  
  
1.  지정 된 함수를 구현 하는 DLL을 만드는 [소스 제어 플러그 인](../../extensibility/source-control-plug-ins.md).  
  
2.  적절 한 레지스트리 항목을 만들어 DLL을 등록 \(에서 설명한 [방법: 소스 제어 플러그 인 설치](../../extensibility/internals/how-to-install-a-source-control-plug-in.md)\).  
  
3.  도우미 UI를 만들고 소스 제어 어댑터 패키지는 \(소스 제어 플러그 인을 통해 소스 제어 기능을 처리 Visual Studio 구성 요소\)에서 메시지가 표시 되 면 표시  
  
 소스 제어 명령에 대 한 응답으로 Visual Studio IDE 기본 작업에 대 한 표준 UI 보여 주고 정보 소스 제어 플러그 인 소스 제어 플러그 인 API에 정의 된 함수를 통해 전달 합니다.  고급 옵션에 대 한 소스 제어 플러그 인에서 자신의 UI를 제공 합니다 예를 들어 소스 제어 프로젝트에 대 한 검색 호출할 수 있습니다.  즉 사용자가 UI의 두 가지 서로 다른 스타일을 함께 소스 제어를 처리 하는 경우 제공 될 수 있습니다 것: Visual Studio 제공 하는 UI 및 UI는 소스 제어 플러그 인을 표시 합니다.  이 고급 소스 제어 작업을 가장 쉽게 확인할 수 있습니다.  
  
### 플러그 인을 구현 하는 단점이  
  
-   고급 기능에 대 한 혼동을 앞에 두 가지 서로 다른 스타일의 인터페이스를 사용자가 볼 수 있습니다.  
  
-   소스 제어 플러그 인 소스 제어 플러그 인 API가 암시적으로 소스 제어 모델에 국한 됩니다.  
  
-   소스 제어 플러그 인 API 일부 소스 제어 시나리오를 너무 제한적일 수 있습니다.  
  
### 플러그 인을 구현 하는 장점  
  
-   소스 제어 플러그 인은 복잡 한 UI를 구현 할 수 있도록 Visual Studio 기본 소스 제어 작업에 대 한 모든 UI를 제공 합니다.  
  
-   엄격한 API 때문에 소스 제어 플러그 인 쉽게 더욱 다양 한 기능을 제공 하도록 외부 소스 제어 프로그램에 상호 작용할 수 있습니다. Visual Studio 너무 많이 하는 방법 소스 제어 기능을 해당 소스 제어 플러그 인 API에 따라 작업 수행 됩니다 수행 됩니다 자동으로 처리 하지 않습니다.  
  
-   보다 Vspackage는 소스 제어 플러그 인을 구현 하는 것이 더 쉽습니다.  
  
## 소스 제어 VSPackage  
 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)]모든 소스 제어 기능 제어 및 Visual Studio 제공 하는 소스 제어 사용자 인터페이스를 완전히 대체와 Visual Studio 통합 되어 있습니다.  소스 제어 VSPackage Visual Studio 등록 되 고 소스 제어 기능을 제공 합니다.  여러 개의 소스 제어 VSPackages Visual Studio 등록할 수 있습니다 하지만 그 중 하나는 한 번에 활성화할 수 있습니다.  활성화 되어 있는 동안 소스 제어 VSPackage 소스 제어 기능 및 모양에 대 한 모든 권한을 Visual Studio 있습니다.  모든 다른 소스 제어 시스템에 등록 될 수 있습니다 VSPackages 비활성화 됩니다 및 모든 UI를 표시 하지 않습니다.  
  
 소스 제어 Vspackage를 구현 하는 "모두 또는 아무것도" 전략이 필요 합니다.  소스 제어 VSPackage 만든 많은 소스 제어 인터페이스와 새 UI 요소 \(대화 상자, 메뉴 및 도구 모음\) 전체 소스 제어 기능을 구현 하는 노력이 상당한을 투자 해야 합니다.  자세한 내용은 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)을 참조하십시오.  
  
### 소스 제어 Vspackage를 구현 하는 단점이  
  
-   있는 VSPackage 여러 Visual Studio 성공적으로 통합 하는 복잡 한 인터페이스를 구현 해야 합니다.  
  
-   있는 VSPackage 원본 컨트롤에 필요한 모든 UI를 제공 해야 합니다. Visual Studio이 영역에서 도움을 제공 합니다.  
  
-   소스 제어 VSPackage Visual Studio 깊숙히 연관 되어 고 기능은 소스 제어 프로그램 외부 버전으로 쉽게 공유할 수 없습니다 있도록 독립 실행형 프로그램으로 작동할 수 없습니다.  
  
### 소스 제어 Vspackage를 구현 하는 장점  
  
-   있는 VSPackage 기능과 소스 제어 UI에 대 한 모든 권한이 있기 때문에 소스 제어에 대 한 완벽 한 인터페이스 제공 됩니다.  
  
-   있는 VSPackage 특정 소스 컨트롤 모델에 제한 되지 않습니다.  
  
## 참고 항목  
 [소스 제어](../../extensibility/internals/source-control.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [소스 제어 VSPackage 만들기](../../extensibility/internals/creating-a-source-control-vspackage.md)   
 [소스 제어의 새로운 기능](../../extensibility/internals/what-s-new-in-source-control.md)
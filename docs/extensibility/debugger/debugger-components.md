---
title: "디버거 구성 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버깅 [Visual Studio], 구성 요소"
  - "구성 요소 [Visual Studio SDK] 디버깅"
  - "디버깅 [디버깅 SDK], 구성 요소"
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
caps.latest.revision: 30
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 30
---
# 디버거 구성 요소
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거는 Vspackage로 구현 되며 전체 디버그 세션을 관리 합니다.  디버그 세션은 다음 요소로 구성 됩니다.  
  
-   **디버그 패키지:** 는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거에서 디버깅 되 고 있는지에 관계 없이 동일한 사용자 인터페이스를 제공 합니다.  
  
-   **세션 디버그 매니저 \(SDM\):** 에 일관성 있는 프로그래밍 인터페이스를 제공의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거를 관리 하는 다양 한 디버깅 엔진입니다.  에 의해 구현 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   **프로세스 디버그 관리자 \(PDM\):** 관리의 실행 중인 인스턴스 모두에 대 한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 수도 있고 디버깅 하 고 있는 모든 프로그램의 목록을 합니다.  에 의해 구현 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
-   **디버그 엔진 \(DE\):** 디버깅 되는 프로그램을 모니터링 하는 SDM 및 PDM, 실행 중인 프로그램의 상태를 통신 하 고 상태를 프로그램의 변수 및 메모리의 실시간 분석으로 식 평가기와 기호 공급자와 상호 작용 합니다.  에 의해 구현 됩니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] \(지원 언어\)에 대 한 타사 공급 업체 직접 실행된 모드를 지원 하 고.  
  
-   **식 계산기 \(EE\):** 변수 및 특정 시점에 프로그램이 중지 되었을 때 사용자가 지정한 식을 동적으로 평가 대 한 지원을 제공 합니다.  에 의해 구현 됩니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] \(지원 언어\)에 대 한 타사 공급 업체는 자신의 언어를 지원 하 고 있습니다.  
  
-   **기호 공급자 \(SP\):** 라고도 기호 처리기에 매핑하는 프로그램의 디버깅 기호 프로그램의 실행 중인 인스턴스를 \(소스 코드 수준 식을 디버깅 및 계산 등\) 의미 있는 정보를 제공할 수 있도록 합니다.  에 의해 구현 됩니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] \(공용 언어 런타임 \[CLR\] 기호 및 프로그램 데이터베이스 \[PDB\] 파일 형식 기호\) 및 제 3 자 공급 업체가 자신의 독점적인 메서드를 디버깅 정보를 저장 합니다.  
  
 다음 다이어그램의 Visual Studio 디버거에서 이러한 요소 간의 관계를 보여 줍니다.  
  
 ![구성 요소 디버깅 개요](~/extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## 단원 내용  
 [패키지를 디버그 합니다.](../../extensibility/debugger/debug-package.md)  
 디버그 패키지 실행에 대해 설명의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸 및 ui를 처리 합니다.  
  
 [디버그 프로세스 관리자](../../extensibility/debugger/process-debug-manager.md)  
 디버깅할 수 있는 프로세스는 관리자가 하에서 PDM의 기능을 소개 합니다.  
  
 [디버그 세션 관리자](../../extensibility/debugger/session-debug-manager.md)  
 IDE를 디버그 세션의 통합 된 보기를 제공 하는 SDM 정의 합니다.  SDM에는 DE 관리합니다.  
  
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)  
 문서는 DE 제공 디버깅 서비스가 있습니다.  
  
 [작업 모드](../../extensibility/debugger/operational-modes.md)  
 IDE 조작할 세 가지 모드의 개요를 제공 합니다: 디자인 모드, 실행된 모드, 중단 모드입니다.  또한 전환 메커니즘을 설명 합니다.  
  
 [식 계산기](../../extensibility/debugger/expression-evaluator.md)  
 런타임에 EE의 용도 설명합니다.  
  
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)  
 변수 및 식을 기호 공급자 구현에 평가 하는 방법에 대해 설명 합니다.  
  
 [시각화 도우미 형식 및 사용자 지정 뷰어](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 내용에 대해 설명 된 시각화 도우미 형식 및 사용자 지정 뷰어 및 식 계산기 어떤 역할 모두를 지원 합니다.  
  
## 관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 디버깅의 주요 아키텍처 개념에 설명 합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 DE에서 동시에 코드, 설명서, 및 식 평가 컨텍스트 내에서 작동 하는 방식을 설명 합니다.  각각의 세 가지 컨텍스트, 위치, 위치, 또는 평가에 관련에 대해 설명합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 고 식을 계산 하는 것과 같은 다양 한 디버깅 작업에 대 한 링크가 포함 되어 있습니다.  
  
## 참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
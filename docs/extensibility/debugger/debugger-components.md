---
title: "디버거 구성 요소 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debugging [Visual Studio], components
- components [Visual Studio SDK], debugging
- debugging [Debugging SDK], components
ms.assetid: 8b8ab77f-a134-495c-be42-3bc51aa62dfb
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 1137c8c5c6041b41e8cbdc0e13d43b6188bd1b1b
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debugger-components"></a>디버거 구성 요소
[!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거는 VSPackage로 구현 되었으며 전체 디버그 세션을 관리 합니다. 디버그 세션에는 다음과 같은 요소가 구성 됩니다.  
  
-   **디버그 패키지가:** 는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버거는 디버깅 하는 관계 없이 동일한 사용자 인터페이스를 제공 합니다.  
  
-   **세션 디버그 관리자 (SDM):** 일관성 있는 프로그래밍 인터페이스를 제공는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다양 한 디버그 엔진의 관리에 대 한 디버거 합니다. 에 의해 구현 되며 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   **프로세스 디버그 관리자 (PDM):** 의 모든 실행 중인 인스턴스에 대 한 관리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 될 수 있는 디버깅 중인 모든 프로그램의 목록입니다. 에 의해 구현 되며 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   **디버그 엔진 (DE):** 디버깅 중인 프로그램을 모니터링 하는 통신은 SDM PDM을 실행 중인 프로그램의 상태 및 실시간 분석을 제공 하는 식 계산기 및 기호 공급자 상호 작용에 프로그램의 메모리 및 변수의 상태입니다. 에 의해 구현 됩니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (에 지 원하는 언어) 및 직접 실행된 시간을 지원 하려는 타사 공급 업체입니다.  
  
-   **식 계산기 (EE):** 변수와 프로그램 특정 지점에서 중지 된 경우 사용자가 제공 하는 식을 동적으로 평가 위한 지원을 제공 합니다. 에 의해 구현 되며 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (에 지 원하는 언어) 및 고유 언어를 지원 하려는 타사 공급 업체.  
  
-   **기호 공급자 (SP):** 호출 또한 기호 처리기는 프로그램의 디버깅 기호에 매핑하여은 프로그램의 실행 중인 인스턴스 하도록 의미 있는 정보 (예: 소스 코드 수준 디버깅 및 식 평가) 제공 될 수 있습니다. 에 의해 구현 되며 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] (공용 언어 런타임 [CLR]에 대 한 기호 및 프로그램 데이터베이스 [PDB] 기호 파일 형식) 및 타사 공급 업체 자신의 소유 메서드가 디버깅 정보를 저장 하 여 합니다.  
  
 다음 다이어그램은 Visual Studio 디버거의 이러한 요소 간의 관계를 보여줍니다.  
  
 ![구성 요소 디버깅 개요](../../extensibility/debugger/media/dbugcompovrview.gif "DBugCompOvrview")  
  
## <a name="in-this-section"></a>섹션 내용  
 [패키지 디버그](../../extensibility/debugger/debug-package.md)  
 실행 되는 디버그 패키지에 설명 된 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸 및 UI의 모든 처리 합니다.  
  
 [프로세스 디버그 관리자](../../extensibility/debugger/process-debug-manager.md)  
 디버깅할 수 있는 프로세스 관리자는 PDM의 기능에 대 한 개요를 제공 합니다.  
  
 [세션 디버그 관리자](../../extensibility/debugger/session-debug-manager.md)  
 IDE에 디버그 세션의 통합된 뷰를 제공 하는 SDM를 정의 합니다. SDM는 DE를 관리합니다.  
  
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)  
 DE 제공 되는 디버깅 서비스에 설명 합니다.  
  
 [작업 모드](../../extensibility/debugger/operational-modes.md)  
 IDE 작동할 수 있는 세 가지 모드의 개요를 제공: 모드, 실행된 모드 및 중단 모드를 디자인 합니다. 전환 메커니즘 에서도 설명 합니다.  
  
 [식 계산기](../../extensibility/debugger/expression-evaluator.md)  
 런타임 시 EE의 용도 설명 합니다.  
  
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)  
 방법, 구현, 기호 공급자 평가 변수 및 식을 설명 합니다.  
  
 [형식 시각화 도우미 및 사용자 지정 뷰어](../../extensibility/debugger/type-visualizer-and-custom-viewer.md)  
 방법에 대해 설명 형식 시각화 도우미와 사용자 지정 뷰어 있고 식 계산기 수행 어떤 역할에서 모두 지원 합니다.  
  
## <a name="related-sections"></a>관련 단원  
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)  
 기본 디버깅 아키텍처 개념을 설명합니다.  
  
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)  
 DE는 동시에 코드, 설명서 및 식 평가 컨텍스트 내에서 작동 방법에 대해 설명 합니다. 세 가지 컨텍스트, 위치, 위치, 또는 그와 관련 된 계산의 각각에 대해 설명합니다.  
  
 [디버깅 작업](../../extensibility/debugger/debugging-tasks.md)  
 프로그램을 시작 하 여 식을 계산 등의 다양 한 디버깅 작업에 대 한 링크를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [시작](../../extensibility/debugger/getting-started-with-debugger-extensibility.md)
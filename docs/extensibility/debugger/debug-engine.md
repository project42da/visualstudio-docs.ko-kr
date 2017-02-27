---
title: "디버그 엔진 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "디버그 엔진"
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# 디버그 엔진
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 인터프리터 또는 운영 체제 실행 제어, 중단점 및 식 평가 같은 디버깅 서비스를 제공 하는 작동 합니다.  DE는 디버깅 중인 프로그램의 상태를 모니터링 하는 데 담당 합니다.  이 작업을 수행 하는 DE 메서드는 무엇이 든 지원 되는 런타임에서 사용 가능한 CPU 또는 Api에서 런타임에 의해 제공 여부는 사용 합니다.  
  
 예를 들어, 공용 언어 런타임 \(CLR\)은 ICorDebugXXX 인터페이스를 통해 실행 중인 프로그램을 모니터링 하는 메커니즘을 제공 합니다.  CLR에서 지원 되는 DE 적절 한 ICorDebugXXX 인터페이스를 사용 하 여 디버깅 하 고 관리 코드 프로그램을 추적 합니다.  이러한 정보를 전달 하는 세션 디버그 관리자 \(SDM\) 그런 다음 상태의 변경 통신의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
> [!NOTE]
>  디버그 엔진에 되 고 있는 프로그램 실행 디버깅 시스템, 특정 런타임을 대상으로 합니다.  CLR 런타임에서 관리 코드에 대 한 고 Win32 공용 언어 런타임은 네이티브 Windows 응용 프로그램입니다.  만든 언어 하나를 이러한 두 런타임 대상 수 있습니다 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 이미 필요한 디버깅 엔진을 제공 합니다.  구현 하는 식 계산기입니다.  
  
## 디버그 엔진 작업  
 모니터링 서비스 DE 인터페이스를 통해 구현 되 고 디버그 패키지 다른 운영 모드 간의 전환에 발생할 수 있습니다.  자세한 내용은 [작업 모드](../../extensibility/debugger/operational-modes.md)를 참조하십시오.  일반적으로 런타임 환경 당 하나의 DE 구현이입니다.  
  
> [!NOTE]
>  Transact\-SQL 대 한 별도 DE 구현 하는 동안 및 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)], VBScript 및 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] 단일 DE를 공유 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅 사용 두 가지 방법 중 하나를 실행 하는 엔진을 디버깅:와 같은 프로세스에는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 셸, 또는 대상 프로그램으로 동일한 프로세스에서 디버깅 되 고.  후자는 일반적으로 디버깅 되는 프로세스는 인터프리터에서 실행 되는 스크립트를 실제로 디버그 엔진 지식을 인터프리터 스크립트를 모니터링할 수 있어야 때 발생 합니다.  참고이 경우, 런타임이 실제로 인터프리터입니다. 디버그 엔진에 대 한 특정 런타임 구현이 있습니다.  또한 단일 DE의 구현 \(예를 들어, 원격 디버깅\) 프로세스와 컴퓨터 경계에 걸쳐 분할할 수 있습니다.  
  
 DE 노출의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 인터페이스입니다.  COM을 통해 통신을 모두입니다.  DE의 처리, 프로세스 out 또는 다른 컴퓨터에서 로드 된 여부에 관계 없이 통신 구성 요소가 변경 되지 않습니다.  
  
 DE 식의 구문을 이해 하는 DE 해당 특정 실행된 시간에 대 한 사용 식 평가기 구성 요소를 사용할 수 있습니다.  DE 언어 컴파일러에 의해 생성 된 기호화 된 디버그 정보에 액세스 하려면 기호 처리기 구성 요소와도 작동 합니다.  자세한 내용은 [식 계산기](../../extensibility/debugger/expression-evaluator.md) 및 [기호 공급자](../../extensibility/debugger/symbol-provider.md)을 참조하십시오.  
  
## 참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)   
 [식 계산기](../../extensibility/debugger/expression-evaluator.md)   
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)
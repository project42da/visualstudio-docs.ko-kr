---
title: "디버그 엔진 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- debug engines
ms.assetid: 148b1efc-ca07-4d8e-bdfc-c723a760c620
caps.latest.revision: 
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 70e572b73f8474f77a17989c790f2e7336f9d7a5
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="debug-engine"></a>디버그 엔진
디버그 엔진 (DE) 작동 인터프리터 또는 운영 체제 실행 제어, 중단점 및 식 평가 같은 디버깅 서비스를 제공 합니다. DE는 디버깅 중인 프로그램의 상태를 모니터링 하는 일을 담당 합니다. 이 위해 수행 하는 DE 모든 메서드를 지원 되는 런타임을 사용할 수 있는 Api 또는 CPU에서 런타임에 제공 되는 여부를 사용 합니다.  
  
 예를 들어, 공용 언어 런타임 (CLR) ICorDebugXXX 인터페이스를 통해 실행 중인 프로그램을 모니터링 하는 메커니즘을 제공 합니다. 지 원하는 CLR DE 디버깅 중인 관리 코드 프로그램을 추적 하는 적절 한 ICorDebugXXX 인터페이스를 사용 합니다. 그런 다음 이러한 정보를 전달 하는 세션 디버그 관리자 (SDM)에 상태의 변경 내용을 통신는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] IDE.  
  
> [!NOTE]
>  디버그 엔진에는 특정 런타임 실행 되 고 있는 프로그램 디버깅 중인 시스템 즉, 대상으로 합니다. CLR은 관리 코드에 대 한 런타임 및 네이티브 Windows 응용 프로그램에 대 한 Win32 런타임이입니다. 이러한 두 개의 런타임, 중 하나를 만들면 언어 대상 수 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 필요한 디버그 엔진을 이미 지정 했습니다. 구현 해야 하는 식 계산기입니다.  
  
## <a name="debug-engine-operation"></a>디버그 엔진 작업  
 모니터링 서비스 DE 인터페이스를 통해 구현 되 고 다른 작업 모드 간에 전환 디버그 패키지가 발생할 수 있습니다. 자세한 내용은 참조 [작동 모드](../../extensibility/debugger/operational-modes.md)합니다. 일반적으로 런 타인 환경 당 하나만 DE 구현이 됩니다.  
  
> [!NOTE]
>  TRANSACT-SQL에 대 한 별도 DE 구현을 상태인 및 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)], VBScript 및 [!INCLUDE[jsprjscript](../../debugger/debug-interface-access/includes/jsprjscript_md.md)] 단일 DE 공유 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]디버깅 디버그 두 가지 방법 중 하나를 실행 하는 엔진:와 같은 프로세스에서는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 골조 또는 대상 프로그램와 동일한 프로세스에서 디버깅 중인 합니다. 두 번째 폼에는 일반적으로 디버깅 중인 프로세스는 인터프리터에서 실행 되는 스크립트에 실제로 디버그 엔진 스크립트를 모니터링 하기 위해 인터프리터의 지식이 있어야 때 발생 합니다. 이 경우 인터프리터는 런타임 실제로; 디버그 엔진은이 특정 런타임 구현에 대 한 합니다. 또한 단일 DE의 구현 (예: 원격 디버깅) 프로세스 및 컴퓨터 경계에 걸쳐 분할 될 수 있습니다.  
  
 DE 노출은 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅 인터페이스입니다. COM.를 통해 모든 통신은 In process, 프로세스 아웃 또는 다른 컴퓨터에서 로드 되는 DE 여부를 구성 요소 통신에는 영향을 주지 않습니다.  
  
 식의 구문을 이해 하기 DE 해당 특정 실행된 시간에 대해 사용할 수 있도록 하는 식 계산기 구성 요소는 DE 작동 합니다. 언어 컴파일러에서 생성 된 기호화 된 디버그 정보에 액세스 하는 기호 처리기 구성 요소는 DE 에서도 작동 합니다. 자세한 내용은 참조 [식 계산기](../../extensibility/debugger/expression-evaluator.md) 및 [기호 공급자](../../extensibility/debugger/symbol-provider.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)   
 [식 계산기](../../extensibility/debugger/expression-evaluator.md)   
 [기호 공급자](../../extensibility/debugger/symbol-provider.md)
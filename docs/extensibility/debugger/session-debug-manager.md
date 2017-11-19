---
title: "세션 관리자 디버그 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- session debug manager, unifying session views
- session debug manager, broadcasting
- debugging [Debugging SDK], session debug manager
- session debug manager
- session debug manager, debug engine multiplexing
- session debug manager, delegating
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 8100c43578c11ae73f26764df74aa17caccc3611
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="session-debug-manager"></a>세션 디버그 관리자
세션 디버그 관리자 (SDM)는 개수에 관계 없이 원하는 수의 여러 컴퓨터에서 여러 프로세스에서 프로그램을 디버깅 디버그 엔진 (DE)을 관리 합니다. 멀티플렉서 디버그 엔진에 뿐은 SDM IDE에 디버그 세션의 통합된 뷰를 제공 합니다.  
  
## <a name="session-debug-manager-operation"></a>세션 디버그 관리자 작업  
 세션 디버그 관리자 (SDM)는 DE를 관리합니다. 컴퓨터에서 동시에 실행 하는 둘 이상의 디버그 엔진 있을 수 있습니다. DEs를 멀티플렉싱 할은 SDM 다양 한 인터페이스는 DEs에서 래핑하고 단일 인터페이스로 IDE에 노출 합니다.  
  
 성능을 향상 시키려면 일부 인터페이스 하지 멀티플렉싱 됩니다. 대신, DE에서 직접 사용 하는 하 고 이러한 인터페이스에 대 한 호출에서 SDM 통과 하지 않습니다. 예를 들어 특정 명령, 메모리 또는 특정 DE로 디버깅 하는 특정 프로그램의 문서를 참조 하기 때문에 메모리, 코드 및 문서 컨텍스트를 사용 하는 인터페이스는 멀티플렉싱 되지 않습니다. 다른 DE 없습니다 해당 수준의 통신에 참여 시킬 필요 합니다.  
  
 모든 컨텍스트는 그렇지 않습니다. 식 계산 컨텍스트 인터페이스에 대 한 호출에서 SDM 수행합니다. 식 평가 중은 SDM 래핑하는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 필요할 수 있는 동일한 프로세스에서 프로그램을 디버깅 하는 여러 DEs를 초래 될 수 있습니다 해당 식을 계산할 때 IDE에 제공 하는 인터페이스 동일한 스레드에 대해 실행 합니다.  
  
 SDM 일반적으로 역할는 위임 메커니즘을 하지만 브로드캐스트 메커니즘으로 작동할 수 있습니다. 예를 들어 식 평가 중에 지정된 된 스레드에서 코드를 실행할 수 있습니다 모든 DEs를 알리기 위해 브로드캐스트 메커니즘으로은 SDM 동작 합니다. 마찬가지로, SDM는 stopping 이벤트를 받으면 하 고 모든 프로그램을 실행 중지 시기를 전파 합니다. 단계를 호출할 때은 SDM 브로드캐스트합니다 하 고 모든 프로그램 실행을 계속할 수 있습니다. 중단점은 모든 DE로도 브로드캐스트 됩니다.  
  
 현재 프로세스, 스레드 또는 스택 프레임은 SDM 추적 하지 않습니다. 프로세스, 프로그램 및 스레드 정보는 특정 디버깅 이벤트와 함께에서 SDM로 전송 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)
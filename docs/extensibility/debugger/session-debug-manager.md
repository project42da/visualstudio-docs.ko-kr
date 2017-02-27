---
title: "디버그 세션 관리자 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "세션 디버그 관리자, 세션 뷰를 통합 합니다."
  - "세션 디버그 관리자, 브로드캐스트"
  - "디버깅 세션 디버그 관리자 [디버깅 SDK]"
  - "디버그 세션 관리자"
  - "세션 디버그 관리자 디버그 엔진 멀티플렉싱"
  - "세션 디버그 관리자, 위임"
ms.assetid: fbb1928d-dddc-43d1-98a4-e23b0ecbae09
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 디버그 세션 관리자
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다양 한 프로그램에서 여러 컴퓨터에서 여러 프로세스를 디버깅할 디버깅 엔진 \(DE\)의 여러 세션 디버그 매니저 \(SDM\)을 관리 합니다.  멀티플렉서는 디버그 엔진을 하는 외에 SDM IDE를 디버그 세션의 통합 된 뷰를 제공 합니다.  
  
## 디버그 관리자 작업 세션  
 세션 디버그 매니저 \(SDM\)에 DE를 관리합니다.  동시에 실행 하는 컴퓨터에 두 개 이상의 디버그 엔진 있을 수 있습니다.  Des는 다 면화 하는 SDM 여러 인터페이스는 DEs에서 래핑하고 IDE는 단일 인터페이스로 노출.  
  
 성능을 향상 시키려면 일부 인터페이스가 멀티플렉싱 됩니다.  대신를 DE에서 직접 사용 되는 및 이러한 인터페이스 호출 SDM을 통해 이동 하지 마십시오.  특정 명령, 메모리 또는 문서에서 특정 프로그램을 특정 DE에서 디버깅 참조 하기 때문에 예를 들어, 메모리, 코드 및 문서 컨텍스트를 사용 하는 인터페이스를 멀티플렉싱 됩니다지 않습니다.  없는 다른 DE 통신 수준에 포함 될 필요가 없습니다.  
  
 모든 컨텍스트는 그렇지 않습니다.  식 계산 컨텍스트의 인터페이스에 대 한 호출 SDM을 통해 이동 하십시오.  식을 계산 하는 동안에 SDM 래핑하는 [IDebugExpression2](../../extensibility/debugger/reference/idebugexpression2.md) 해당 식을 계산할 때 동일한 스레드에서 실행 됩니다 동일한 프로세스에서 프로그램을 디버깅 하는 여러 DEs 것일 수 있으므로 IDE를 제공 하는 인터페이스입니다.  
  
 SDM는 일반적으로 위임 메커니즘에 따라 역할을 하지만 브로드캐스트 메커니즘으로 역할을 할 수 있습니다.  예를 들어, 식을 계산 하는 동안에 SDM 코드 지정 된 스레드를 실행할 수 있는지 모든 Des를 알리기 위해 브로드캐스트 메커니즘으로 역할을 합니다.  마찬가지로, 중지 이벤트는 SDM을 받으면 모든 프로그램 들은 실행 중지 해야 브로드캐스트합니다.  단계를 호출 하면 실행을 계속 수 있습니다 모든 프로그램에는 SDM 브로드캐스트합니다.  또한 중단점 마다 DE에 브로드캐스팅합니다.  
  
 현재 프로그램이 나 스레드, 스택 프레임은 SDM를 추적 하지 않습니다.  프로세스, 프로그램 및 스레드 정보를 전송 하는 SDM 특정 디버깅 이벤트와 함께에서 합니다.  
  
## 참고 항목  
 [디버그 엔진](../../extensibility/debugger/debug-engine.md)   
 [디버거 구성 요소](../../extensibility/debugger/debugger-components.md)   
 [디버거 컨텍스트](../../extensibility/debugger/debugger-contexts.md)
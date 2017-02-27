---
title: "중단점 (Visual Studio SDK) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단점"
ms.assetid: acfcabed-9f2f-436c-ad18-7ca2f45d631b
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# 중단점 (Visual Studio SDK)
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

중단점의 세 가지가: 보류, 바인딩, 오류입니다.  
  
 **보류 중단점 A:**  
  
-   하나 이상의 프로그램에 하나 이상의 코드 컨텍스트 중단점에 바인딩하는 데 필요한 모든 정보가 포함 된 추상화가입니다.  때마다 로드 하는 원인 코드 디버깅 되는 프로그램 디버그 엔진 보류 중단점을 모두 바인딩할 수 있습니다 경우 보려면 확인 합니다.  
  
     있는 보류 중인 중단점 절대로 코드에 바인딩합니다 있지만 오히려 수집, 생성 되는 모든 바인딩된 중단점 포함 되었다고 합니다.  
  
-   표시 되는  [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md) 인터페이스입니다.  
  
 **바인딩된 중단점:**  
  
-   중단점에 대 한 추상화와 관련 된 또는 단일 코드 컨텍스트에 바인딩할.  각각의 바인딩된 중단점은 보류 중단점에 생성 됩니다.  하지만 보류 중단점 여러 개의 바인딩된 중단점이 생성 수는 있습니다.  
  
     코드를 로드 되 면 바인딩된 중단점 언바운드 및 삭제 될 수 있습니다.  
  
-   표시 되는  [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md) 인터페이스입니다.  
  
 **있는 오류 중단점:**  
  
-   보류 중단점은 코드 컨텍스트에 바인딩하려면 시도 중 오류를 설명 하는 추상화가입니다.  오류 중단점 중 오류 위치 또는 중단점 식에 설명합니다.  자세한 내용은  [중단점이 바인딩](../../extensibility/debugger/binding-breakpoints.md).  
  
     중단점 오류는 오류 또는 경고 수 있습니다.  
  
-   표시 되는  [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) 인터페이스입니다.  
  
## 참고 항목  
 [Programs](../../extensibility/debugger/programs.md)   
 [디버거 개념](../../extensibility/debugger/debugger-concepts.md)   
 [코드 컨텍스트](../../extensibility/debugger/code-context.md)   
 [IDebugBoundBreakpoint2](../../extensibility/debugger/reference/idebugboundbreakpoint2.md)   
 [IDebugPendingBreakpoint2](../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpoint2](../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)
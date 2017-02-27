---
title: "중단점 도착 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단점 적중, 디버깅 [디버깅 SDK]"
  - "중단점에 도달"
ms.assetid: a77816e3-b15b-46a0-90cd-be7242e4d6c9
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 중단점 도착
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\)를 실행 하거나 한 단계씩 실행 하는 동안 중단점에 도달할 때 다음 과정을입니다.  
  
## 중단점 적중 문제 해결  
  
1.  DE 센드는  [IDebugBreakpointEvent2](../../extensibility/debugger/reference/idebugbreakpointevent2.md) 로 인터페이스는  **EVENT\_SYNC\_STOP**.  
  
2.  호출 세션이 디버그 매니저 \(SDM\)  [IDebugBreakpointEvent2:::EnumBreakpoints](../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md) 적중 된 중단점을 가져올 수 있습니다.  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)
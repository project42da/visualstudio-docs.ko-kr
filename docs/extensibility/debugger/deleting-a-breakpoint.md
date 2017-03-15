---
title: "중단점 삭제 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단점을 삭제"
  - "디버깅 [디버깅 SDK], 중단점 삭제"
ms.assetid: 75a046cc-d20a-4c79-ad2d-1f18426ac5d0
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# 중단점 삭제
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음은 보류 중단점을 삭제 하는 경우 프로세스를입니다.  
  
## 삭제 프로세스  
 세션 디버그 매니저 \(SDM\)를 호출 하 여  [IDebugPendingBreakpoint2::Delete](../../extensibility/debugger/reference/idebugpendingbreakpoint2-delete.md) 보류 중단점 및 바인딩된 모든 중단점을 제거 하는 방법 연결에서.  
  
> [!NOTE]
>  호출 하 여 단일 바인딩된 중단점을 삭제  [IDebugBoundBreakpoint2::Delete](../../extensibility/debugger/reference/idebugboundbreakpoint2-delete.md).  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)
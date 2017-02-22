---
title: "중단점 오류 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "중단점 오류"
  - "디버깅 [디버깅 SDK] 중단점 오류"
  - "오류 [디버깅 SDK]"
ms.assetid: 79221c6b-a924-4c8e-a778-e312e4e0c0c8
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 중단점 오류
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 중단점을 코드에 바인딩하려면 시도 하는 경우 해당 프로세스에 설명 하지만 실패 합니다.  
  
## 중단점 오류 문제 해결  
  
1.  디버그 엔진 \(DE\)을 보냅니다를  [IDebugBreakpointErrorEvent2](../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md) 세션 디버그 매니저 \(SDM\)에 있습니다.  
  
2.  SDM 호출  [IDebugBreakpointErrorEvent2::GetErrorBreakpoint](../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) \(IDebugErrorBreakpoint2 \*\* `ppErrorBP`\) 오류 중단점을 가져올 수 있습니다.  
  
3.  SDM 호출  [IDebugErrorBreakpoint2::GetPendingBreakpoint](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md) 은 보류 중단점 중단점 오류 시작 얻을 수 있습니다.  
  
4.  SDM 호출  [IDebugErrorBreakpoint2::GetBreakpointResolution](../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md) 이유는 오류 중단점 바인딩하지 못했습니다 이유를 얻을 수 있습니다.  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)
---
title: "중단 모드에서 단계별 실행 | Microsoft Docs"
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
  - "중단 모드 단계별 실행"
  - "중단 모드에서 단계별 실행"
  - "중단 모드에서 단계별 실행, 디버깅 [디버깅 SDK]"
ms.assetid: b08dc8ee-6c63-4462-a097-6f525cfbb35a
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# 중단 모드에서 단계별 실행
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다음 디버거가 중단 모드에 있는 코드를 단계별로 실행 해야 하는 경우에 발생 하는 프로세스를 설명 합니다.  
  
## 프로세스를 한 단계씩 실행  
  
1.  호출  [IDebugProgram2::Step](../../extensibility/debugger/reference/idebugprogram2-step.md) 와  [STEPKIND](../../extensibility/debugger/reference/stepkind.md) 및  [STEPUNIT](../../extensibility/debugger/reference/stepunit.md) 인수는 단계를 실행 합니다.  
  
2.  단계가 완료 되 면 보내기는  [IDebugStepCompleteEvent2](../../extensibility/debugger/reference/idebugstepcompleteevent2.md) 중지 이벤트입니다.  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)
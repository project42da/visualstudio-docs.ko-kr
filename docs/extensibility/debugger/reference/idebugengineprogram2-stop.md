---
title: "IDebugEngineProgram2::Stop | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngineProgram2::Stop"
helpviewer_keywords: 
  - "IDebugEngineProgram2::Stop"
ms.assetid: 6e1c3d56-fb67-4a5b-80f9-8ee5131972bf
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngineProgram2::Stop
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램에서 실행 중인 모든 스레드를 중지 합니다.  
  
## 구문  
  
```cpp#  
HRESULT Stop(   
   void   
);  
```  
  
```c#  
int Stop();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 프로그램은 multi\-program 환경에서 디버깅 되는 동안이 메서드가 호출 됩니다.  있는 일부 다른 프로그램이 중지 이벤트를 수신 하면이 메서드는이 프로그램에서 호출 됩니다.  이 메서드의 구현은 비동기 있어야 합니다. 즉, 모든 스레드가이 메서드가 반환 되기 전에 중지 해야 합니다.  이 메서드의 구현을 호출으로 같은 간단한 것일 수도 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md) 메서드가이 프로그램에.  
  
 디버그 이벤트에 응답 하 고 전송 됩니다.  
  
## 참고 항목  
 [IDebugEngineProgram2](../../../extensibility/debugger/reference/idebugengineprogram2.md)   
 [CauseBreak](../../../extensibility/debugger/reference/idebugprogram2-causebreak.md)
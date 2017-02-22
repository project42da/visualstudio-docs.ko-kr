---
title: "DEBUG_REASON | Microsoft Docs"
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
  - "DEBUG_REASON"
helpviewer_keywords: 
  - "DEBUG_REASON 열거형"
ms.assetid: ad2ee898-8648-4671-9078-d32873862346
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# DEBUG_REASON
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로세스 디버깅을 위해 시작 된 이유를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
typedef DWORD DEBUG_REASON;  
```  
  
```c#  
public enum enum_DEBUG_REASON {  
   DEBUG_REASON_ERROR         = 0,  
   DEBUG_REASON_USER_LAUNCHED = 1,  
   DEBUG_REASON_USER_ATTACHED = 2,  
   DEBUG_REASON_AUTO_ATTACHED = 3,  
   DEBUG_REASON_CAUSALITY     = 4  
};  
```  
  
#### 매개 변수  
 DEBUG\_REASON\_ERROR  
 미지정 오류가 발생 했습니다 \(어떤 다른 맞춤 이유로 때 기본 조건으로 사용 됩니다\).  
  
 DEBUG\_REASON\_USER\_LAUNCHED  
 사용자 요청에 과정을 시작 했습니다.  
  
 DEBUG\_REASON\_USER\_ATTACHED  
 사용자가 이미 실행 중인 프로세스에 연결 되었습니다.  
  
 DEBUG\_REASON\_AUTO\_ATTACHED  
 시작 될 때 프로세스에 자동으로 연결 되었습니다.  
  
 DEBUG\_REASON\_CAUSALITY  
 때문에 프로세스가 시작 된는  *에서 Just\-in\-time* \(JIT\) 디버깅 이벤트입니다.  
  
## 설명  
 반환 되는 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md) 메서드.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [GetDebugReason](../../../extensibility/debugger/reference/idebugprocess3-getdebugreason.md)
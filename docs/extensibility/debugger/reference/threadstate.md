---
title: "THREADSTATE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "THREADSTATE"
helpviewer_keywords: 
  - "THREADSTATE 열거형"
ms.assetid: 62efdd7c-25b1-4fd3-9d06-ac1830a418a9
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# THREADSTATE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스레드의 상태를 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
typedef DWORD THREADSTATE;  
```  
  
```c#  
public enum enum_THREADSTATE {   
   THREADSTATE_RUNNING = 0x0001,  
   THREADSTATE_STOPPED = 0x0002,  
   THREADSTATE_FRESH   = 0x0003,  
   THREADSTATE_DEAD    = 0x0004,  
   THREADSTATE_FROZEN  = 0x0005  
};  
```  
  
## Members  
 THREADSTATE\_RUNNING  
 스레드가 실행 중인지를 나타냅니다.  
  
 THREADSTATE\_STOPPED  
 중단점의 스레드가 중지 되었음을 나타냅니다.  
  
 THREADSTATE\_FRESH  
 스레드 작성 된 있지만 코드가 아직 실행 되 고 있음을 나타냅니다.  
  
 THREADSTATE\_DEAD  
 스레드가 비활성화 된 나타냅니다.  
  
 THREADSTATE\_FROZEN  
 스레드가 고정 된 나타냅니다 \(를 실행 하지 않아도 수행할 수 있습니다\).  
  
## 설명  
 사용 되는 `dwThreadState` 필드는 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md) 구조입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [THREADPROPERTIES](../../../extensibility/debugger/reference/threadproperties.md)
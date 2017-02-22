---
title: "STEPKIND | Microsoft Docs"
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
  - "STEPKIND"
helpviewer_keywords: 
  - "STEPKIND 열거형"
ms.assetid: d3d8cf76-24bf-455e-803e-0e3e28f0b262
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# STEPKIND
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

단계별 코드 실행 단계 유형을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum enum_STEPKIND {   
   STEP_INTO      = 0,  
   STEP_OVER      = 1,  
   STEP_OUT       = 2,  
   STEP_BACKWARDS = 3  
};  
typedef DWORD STEPKIND;  
```  
  
```c#  
public enum enum_STEPKIND {   
   STEP_INTO      = 0,  
   STEP_OVER      = 1,  
   STEP_OUT       = 2,  
   STEP_BACKWARDS = 3  
};  
```  
  
## Members  
 STEP\_INTO  
 단계 함수입니다.  
  
 STEP\_OVER  
 함수에 사용 되는 단계입니다.  
  
 STEP\_OUT  
 함수 외부로 나갑니다.  
  
 STEP\_BACKWARDS  
 단계별 함수입니다.  
  
## 설명  
 인수로 전달 되는 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md) 방법입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [열거형](../../../extensibility/debugger/reference/enumerations-visual-studio-debugging.md)   
 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md)
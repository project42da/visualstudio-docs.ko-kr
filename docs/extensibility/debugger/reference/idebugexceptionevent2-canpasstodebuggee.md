---
title: "IDebugExceptionEvent2::CanPassToDebuggee | Microsoft Docs"
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
  - "IDebugExceptionEvent2::CanPassToDebuggee"
helpviewer_keywords: 
  - "IDebugExceptionEvent2::CanPassToDebuggee"
ms.assetid: ae4bbe0a-fbe1-49be-a310-ea64279a434b
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugExceptionEvent2::CanPassToDebuggee
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 실행을 다시 시작 하는 경우에 디버깅 중인 프로그램에이 예외를 전달 하는 옵션을 지원 하는지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT CanPassToDebuggee(  
   void  
);  
```  
  
```c#  
int CanPassToDebuggee();  
```  
  
## 반환 값  
 반환 `S_OK` \(예외 프로그램으로 전달 될 수 있습니다\) 또는 `S_FALSE` \(예외를 전달할 수 없습니다\).  
  
## 설명  
 DE 디버기에 전달에 대 한 기본 작업을 해야 합니다.  IDE 나타날 수 있습니다 있는 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md) 호출 하 고 이벤트는 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md) 메서드를 호출 하지 않고는 `CanPassToDebuggee` 메서드.  따라서 DE은 기본 경우에 또는 예외를 전달 해야 합니다.  
  
## 참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md)
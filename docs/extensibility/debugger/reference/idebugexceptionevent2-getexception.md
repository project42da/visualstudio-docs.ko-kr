---
title: "IDebugExceptionEvent2::GetException | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugExceptionEvent2::GetException"
helpviewer_keywords: 
  - "IDebugExceptionEvent2::GetException"
ms.assetid: 7c98f41d-322b-4e72-a514-cbd4823eb70d
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugExceptionEvent2::GetException
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 이벤트가 발생 하는 예외에 대 한 자세한 설명을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetException(   
   EXCEPTION_INFO* pExceptionInfo  
);  
```  
  
```c#  
int GetException(   
   EXCEPTION_INFO[] pExceptionInfo  
);  
```  
  
#### 매개 변수  
 `pExceptionInfo`  
 \[in, out\] [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md) 구조는 예외에 대 한 설명으로 채웁니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 \[C \+ \+에만\] 호출자가 임의의 문자열을 확보에 대 한 책임을 지지는 [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md) 구조 및 해제는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 구조에 있는 개체입니다.  
  
## 참고 항목  
 [IDebugExceptionEvent2](../../../extensibility/debugger/reference/idebugexceptionevent2.md)   
 [EXCEPTION\_INFO](../../../extensibility/debugger/reference/exception-info.md)   
 [IDebugEvent2](../../../extensibility/debugger/reference/idebugevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
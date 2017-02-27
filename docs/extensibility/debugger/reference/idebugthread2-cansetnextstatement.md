---
title: "IDebugThread2::CanSetNextStatement | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugThread2::CanSetNextStatement"
helpviewer_keywords: 
  - "IDebugThread2::CanSetNextStatement"
ms.assetid: 7014af80-ff4f-4790-a34b-0528918d1fa3
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugThread2::CanSetNextStatement
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

지정 된 스택 프레임을 현재 명령 포인터를 설정할 수 있는지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT CanSetNextStatement (   
   IDebugStackFrame2*  pStackFrame,  
   IDebugCodeContext2* pCodeContext  
);  
```  
  
```c#  
int CanSetNextStatement (   
   IDebugStackFrame2  pStackFrame,  
   IDebugCodeContext2 pCodeContext  
);  
```  
  
#### 매개 변수  
 `pStackFrame`  
 나중에 사용 하도록 예약 됩니다. null 값으로 설정 합니다.  Null 값이 있으면 현재 스택 프레임을 사용 합니다.  
  
 `pCodeContext`  
 \[in\] [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 실행 될 코드 위치를 설명 하는 개체와 그 컨텍스트.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드가 반환 하면 `S_OK`, 다음 호출 하는 [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md) 실제로 다음 문을 설정 하는 메서드.  
  
## 참고 항목  
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)   
 [SetNextStatement](../../../extensibility/debugger/reference/idebugthread2-setnextstatement.md)
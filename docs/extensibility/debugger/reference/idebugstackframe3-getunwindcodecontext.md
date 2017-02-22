---
title: "IDebugStackFrame3::GetUnwindCodeContext | Microsoft Docs"
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
  - "IDebugStackFrame3::GetUnwindCodeContext"
helpviewer_keywords: 
  - "IDebugStackFrame3::GetUnwindCodeContext 메서드"
ms.assetid: b25f7e7d-2b24-48e4-93b3-829e61d73ebf
caps.latest.revision: 6
caps.handback.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugStackFrame3::GetUnwindCodeContext
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

스택 작업을 해제 하는 경우 위치를 나타내는 코드 컨텍스트를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetUnwindCodeContext(  
   IDebugCodeContext2 **ppCodeContext  
);  
```  
  
```c#  
int GetUnwindCodeContext(  
   out IDebugCodeContext2 ppCodeContext  
);  
```  
  
#### 매개 변수  
 `ppCodeContext`  
 \[out\] 반환 된 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md) 스택 해제 발생 한 경우 코드가 맞는 위치를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 스택 해제 후 코드 컨텍스트 위치를 반환할 수 있습니다 경우에이 반드시 스택 해제 현재 스택 프레임에서 실제로 발생할 수 있습니다 의미는 아닙니다.  
  
## 참고 항목  
 [IDebugStackFrame3](../../../extensibility/debugger/reference/idebugstackframe3.md)   
 [IDebugCodeContext2](../../../extensibility/debugger/reference/idebugcodecontext2.md)
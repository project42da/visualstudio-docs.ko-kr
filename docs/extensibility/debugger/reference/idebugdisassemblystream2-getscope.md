---
title: "IDebugDisassemblyStream2::GetScope | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugDisassemblyStream2::GetScope"
helpviewer_keywords: 
  - "IDebugDisassemblyStream2::GetScope"
ms.assetid: 71c6e632-642a-42d8-a995-77e4ac190a5b
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugDisassemblyStream2::GetScope
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디스어셈블리 스트림 범위를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetScope(   
   DISASSEMBLY_STREAM_SCOPE* pdwScope  
);  
```  
  
```c#  
int GetScope(   
   out enum_ DISASSEMBLY_STREAM_SCOPE pdwScope  
);  
```  
  
#### 매개 변수  
 `pdwScope`  
 \[out\] 값을 반환의 [DISASSEMBLY\_STREAM\_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md) 이 분해 스트림 범위를 설명 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 범위는 디스어셈블리를 예를 들어 함수 또는 전체 모듈을 수 있습니다.  
  
## 참고 항목  
 [IDebugDisassemblyStream2](../../../extensibility/debugger/reference/idebugdisassemblystream2.md)   
 [DISASSEMBLY\_STREAM\_SCOPE](../../../extensibility/debugger/reference/disassembly-stream-scope.md)
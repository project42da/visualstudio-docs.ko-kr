---
title: "IDebugMemoryContext2::GetInfo | Microsoft Docs"
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
  - "IDebugMemoryContext2::GetInfo"
helpviewer_keywords: 
  - "GetInfo 메서드"
  - "IDebugMemoryContext2::GetInfo 메서드"
ms.assetid: 08c7f091-1816-4d64-8834-f9ecaac5c58d
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugMemoryContext2::GetInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

검색은 [CONTEXT\_INFO](../../../extensibility/debugger/reference/context-info.md) 컨텍스트를 설명 하는 구조입니다.  
  
## 구문  
  
```cpp#  
HRESULT GetInfo(   
   CONTEXT_INFO_FIELDS dwFields,  
   CONTEXT_INFO*       pInfo  
);  
```  
  
```c#  
int GetInfo(  
   enum_CONTEXT_INFO_FIELDS dwFields,   
   CONTEXT_INFO[]           pinfo  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 플래그의 조합을 [CONTEXT\_INFO\_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md) 필드를 지정 하는 열거형의 [CONTEXT\_INFO](../../../extensibility/debugger/reference/context-info.md) 구조에 있는 수에.  
  
 `pInfo`  
 \[in, out\] `CONTEXT_INFO` 을 입력 하는 구조입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugMemoryContext2](../../../extensibility/debugger/reference/idebugmemorycontext2.md)   
 [CONTEXT\_INFO\_FIELDS](../../../extensibility/debugger/reference/context-info-fields.md)   
 [CONTEXT\_INFO](../../../extensibility/debugger/reference/context-info.md)
---
title: "IDebugPropertyCreateEvent2::GetDebugProperty | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPropertyCreateEvent2::GetDebugProperty"
helpviewer_keywords: 
  - "IDebugPropertyCreateEvent2::GetDebugProperty"
ms.assetid: d7e43183-444c-4417-af19-82e28229f83a
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPropertyCreateEvent2::GetDebugProperty
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

새 속성을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDebugProperty (   
   IDebugProperty2** ppProperty  
);  
```  
  
```c#  
int GetDebugProperty (   
   out IDebugProperty2 ppProperty  
);  
```  
  
#### 매개 변수  
 `ppProperty`  
 \[out\] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 의 새 속성을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPropertyCreateEvent2](../../../extensibility/debugger/reference/idebugpropertycreateevent2.md)   
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
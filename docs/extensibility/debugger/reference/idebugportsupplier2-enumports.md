---
title: "IDebugPortSupplier2::EnumPorts | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2::EnumPorts"
helpviewer_keywords: 
  - "IDebugPortSupplier2::EnumPorts"
ms.assetid: 88b57fd2-eba1-44fa-bd34-cf2ad2b1ff87
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortSupplier2::EnumPorts
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자가 제공 하는 모든 포트의 목록을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT EnumPorts(   
   IEnumDebugPorts2** ppEnum  
);  
```  
  
```c#  
int EnumPorts(   
   out IEnumDebugPorts2 ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md) 제공한 포트 목록이 들어 있는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IEnumDebugPorts2](../../../extensibility/debugger/reference/ienumdebugports2.md)
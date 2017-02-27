---
title: "IDebugPortSupplier2::GetPortSupplierId | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2::GetPortSupplierId"
helpviewer_keywords: 
  - "IDebugPortSupplier2::GetPortSupplierId"
ms.assetid: 741d0829-0943-49bf-b56e-61e836043006
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortSupplier2::GetPortSupplierId
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자 식별자를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPortSupplierId(   
   GUID* pguidPortSupplier  
);  
```  
  
```c#  
HRESULT GetPortSupplierId(   
   out Guid pguidPortSupplier  
);  
```  
  
#### 매개 변수  
 `pguidPortSupplier`  
 \[out\] 포트 공급자의 GUID를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
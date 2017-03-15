---
title: "IDebugPortSupplier2::GetPortSupplierName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortSupplier2::GetPortSupplierName"
helpviewer_keywords: 
  - "IDebugPortSupplier2::GetPortSupplierName"
ms.assetid: e4c368ab-640d-4b5b-9f74-810dc9364d8f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugPortSupplier2::GetPortSupplierName
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자 이름을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPortSupplierName(   
   BSTR* pbstrName  
);  
```  
  
```c#  
int GetPortSupplierName(   
   out string pbstrName  
);  
```  
  
#### 매개 변수  
 `pbstrName`  
 \[out\] 포트 공급자 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)
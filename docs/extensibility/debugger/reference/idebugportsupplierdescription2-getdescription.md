---
title: "IDebugPortSupplierDescription2::GetDescription | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IDebugPortSupplierDescription2::GetDescription"
ms.assetid: bff5f536-1cd1-4313-8856-db7b05818305
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugPortSupplierDescription2::GetDescription
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

포트 공급자에 대 한 설명 및 설명 메타 데이터를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDescription(  
   PORT_SUPPLIER_DESCRIPTION_FLAGS *pdwFlags,  
   BSTR *pbstrText  
);  
```  
  
```c#  
public int GetDescription(  
   out enum_PORT_SUPPLIER_DESCRIPTION_FLAGS pdwFlags,  
   out string pbstrText  
);  
```  
  
#### 매개 변수  
 `pdwFlags`  
 \[out\] 메타 데이터 플래그에 대해 설명 합니다.  
  
 `pbstrText`  
 \[out\] 포트 공급자에 대 한 설명입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugPortSupplierDescription2](../../../extensibility/debugger/reference/idebugportsupplierdescription2.md)
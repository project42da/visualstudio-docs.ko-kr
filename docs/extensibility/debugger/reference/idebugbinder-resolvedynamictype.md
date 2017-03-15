---
title: "IDebugBinder::ResolveDynamicType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBinder::ResolveDynamicType"
helpviewer_keywords: 
  - "IDebugBinder::ResolveDynamicType 메서드"
ms.assetid: 2c36ef92-5b44-4cfd-988e-54a2e5a6710c
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugBinder::ResolveDynamicType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 정확한 형식의 변수를 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT ResolveDynamicType (  
   IDebugDynamicField *pDynamic,  
   IDebugField       **ppResolved  
);  
```  
  
```c#  
int ResolveDynamicType(  
   IDebugDynamicField pDynamic,   
   out IDebugField    ppResolved  
);  
```  
  
#### 매개 변수  
 `pDynamic`  
 \[in\] [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md) 변수의 형식을 표시 합니다.  
  
 `ppResolved`  
 \[out\] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 변수 형식에 대 한 특정 정보를 제공 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugDynamicField](../../../extensibility/debugger/reference/idebugdynamicfield.md)
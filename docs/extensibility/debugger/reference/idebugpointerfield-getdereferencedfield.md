---
title: "IDebugPointerField::GetDereferencedField | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPointerField::GetDereferencedField"
helpviewer_keywords: 
  - "IDebugPointerField::GetDereferencedField 메서드"
ms.assetid: 8de988ab-cd79-4287-be72-3c900f2fe407
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugPointerField::GetDereferencedField
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 가리키는 포인터가 개체가 개체의 형식을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDereferencedField(  
   IDebugField** ppField  
);  
```  
  
```c#  
int GetDereferencedField(  
   out IDebugField ppField  
);  
```  
  
#### 매개 변수  
 `ppField`  
 \[out\] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 대상 개체 형식을 설명 하는.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 예를 들어, if는 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md) 개체에 정수를 가리키는 있는 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 이 메서드의 반환 형식은 해당 정수 형식에 설명 합니다.  
  
## 참고 항목  
 [IDebugPointerField](../../../extensibility/debugger/reference/idebugpointerfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
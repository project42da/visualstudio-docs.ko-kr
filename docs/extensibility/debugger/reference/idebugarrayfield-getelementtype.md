---
title: "IDebugArrayField::GetElementType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugArrayField::GetElementType"
helpviewer_keywords: 
  - "IDebugArrayField::GetElementType 메서드"
ms.assetid: c46bf625-0a48-4cbb-8f1f-286356f2c065
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugArrayField::GetElementType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

요소 형식을에 배열에 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetElementType(   
   IDebugField** ppType  
);  
```  
  
```c#  
int GetElementType(  
   out IDebugField ppType  
);  
```  
  
#### 매개 변수  
 `ppType`  
 \[out\] 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 형식의 요소를 설명 하는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md) 개체 가정 배열의 모든 요소가 같은 종류 인지.  
  
## 참고 항목  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
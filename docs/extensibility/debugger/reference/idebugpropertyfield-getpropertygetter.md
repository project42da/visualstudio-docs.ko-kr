---
title: "IDebugPropertyField::GetPropertyGetter | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPropertyField::GetPropertyGetter"
helpviewer_keywords: 
  - "IDebugPropertyField::GetPropertyGetter 메서드"
ms.assetid: ab9f861a-42ad-4a82-9ae6-2606176f755a
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugPropertyField::GetPropertyGetter
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 속성을 가져오는 메서드를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetPropertyGetter(   
   IDebugMethodField** ppField  
);  
```  
  
```cpp#  
int GetPropertyGetter(  
   out IDebugMethodField ppField  
);  
```  
  
#### 매개 변수  
 `ppField`  
 \[out\] 반환 된 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md) 속성을 가져오는 메서드를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 속성을 설정 하는 메서드를 가져오려면 [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md) 메서드를 호출 합니다.  
  
## 참고 항목  
 [IDebugPropertyField](../../../extensibility/debugger/reference/idebugpropertyfield.md)   
 [GetPropertySetter](../../../extensibility/debugger/reference/idebugpropertyfield-getpropertysetter.md)   
 [IDebugMethodField](../../../extensibility/debugger/reference/idebugmethodfield.md)
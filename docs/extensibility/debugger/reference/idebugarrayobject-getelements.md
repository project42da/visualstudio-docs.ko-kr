---
title: "IDebugArrayObject::GetElements | Microsoft Docs"
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
  - "IDebugArrayObject::GetElements"
helpviewer_keywords: 
  - "IDebugArrayObject::GetElements 메서드"
ms.assetid: f6a6262f-5183-46ce-8a45-33ef46088b98
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugArrayObject::GetElements
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열의 모든 요소에 대 한 열거자를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetElements(   
   IEnumDebugObjects** ppEnum  
);  
```  
  
```c#  
int GetElements(  
   out IEnumDebugObjects ppEnum  
);  
```  
  
#### 매개 변수  
 `ppEnum`  
 \[out\] 반환 된 [IEnumDebugObjects](../../../extensibility/debugger/reference/ienumdebugobjects.md) 는 모든 요소를 열거할 수 있는 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용 하는 대신에 [GetCount](../../../extensibility/debugger/reference/idebugarrayobject-getcount.md) 및 [GetElement](../../../extensibility/debugger/reference/idebugarrayobject-getelement.md) 요소를 반복 하는 방법.  
  
## 참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
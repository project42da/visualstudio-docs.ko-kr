---
title: "IDebugBinder::GetFunctionObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugBinder::GetFunctionObject"
helpviewer_keywords: 
  - "IDebugBinder::GetFunctionObject 메서드"
ms.assetid: 8fb789df-8f30-420d-8ca5-bb496a6738f1
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugBinder::GetFunctionObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드를 가져옵니다는 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 함수의 매개 변수를 생성 하는 데 사용 되는 개체입니다.  
  
## 구문  
  
```cpp#  
HRESULT GetFunctionObject(   
   IDebugFunctionObject **ppFunction  
);  
```  
  
```c#  
int GetFunctionObject(  
   out IDebugFunctionObject ppFunction  
);  
```  
  
#### 매개 변수  
 `ppFunction`  
 \[out\] 반환은 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 함수 매개 변수를 만드는 데 사용 되는 인터페이스입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
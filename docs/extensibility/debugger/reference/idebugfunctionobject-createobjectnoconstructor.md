---
title: "IDebugFunctionObject::CreateObjectNoConstructor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugFunctionObject::CreateObjectNoConstructor"
helpviewer_keywords: 
  - "IDebugFunctionObject::CreateObjectNoConstructor 메서드"
ms.assetid: 4e2bd6d5-f4bd-4c10-a998-3db451c9a0c8
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugFunctionObject::CreateObjectNoConstructor
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

개체를 생성자로 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT CreateObjectNoConstructor(   
   IDebugField*   pClassObject,  
   IDebugObject** ppObject  
);  
```  
  
```c#  
int CreateObjectNoConstructor(  
   IDebugField      pClassField,   
   out IDebugObject ppObject  
);  
```  
  
#### 매개 변수  
 `pClassObject`  
 \[in\] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 만들 수 있는 개체의 형식을 나타내는 개체입니다.  
  
 `ppObject`  
 \[out\] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) , 새로 만들어진된 개체를 나타내는.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 구조 또는으로 표시 되며 함수에는 매개 변수입니다 \(해당 하는 생성자가 필요 하지 않습니다\) 복합 형식 인스턴스를 나타내는 개체를 만드는 데이 메서드를 호출 하 여 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
 생성자는 개체 매개 변수를 요구 하는 경우 호출 하는 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md) 메서드.  
  
## 참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObject](../../../extensibility/debugger/reference/idebugfunctionobject-createobject.md)
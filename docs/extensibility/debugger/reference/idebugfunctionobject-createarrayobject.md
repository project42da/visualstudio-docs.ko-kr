---
title: "IDebugFunctionObject::CreateArrayObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugFunctionObject::CreateArrayObject"
helpviewer_keywords: 
  - "IDebugFunctionObject::CreateArrayObject 메서드"
ms.assetid: a380e53c-15f1-401f-927f-f366eea789e6
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugFunctionObject::CreateArrayObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열 개체를 만듭니다.  이 배열의 기본 형식 중 하나를 포함 하거나 개체 인스턴스 값입니다.  
  
## 구문  
  
```cpp#  
HRESULT CreateArrayObject(   
   OBJECT_TYPE    ot,  
   IDebugField*   pClassField,  
   DWORD          dwRank,  
   DWORD          dwDims[],  
   DWORD          dwLowBounds[],  
   IDebugObject** ppObject  
);  
```  
  
```c#  
int CreateArrayObject(  
   enum_OBJECT_TYPE ot,   
   IDebugField      pClassField,   
   uint             dwRank,   
   uint[]           dwDims,   
   uint[]           dwLowBounds,   
   out IDebugObject ppObject  
);  
```  
  
#### 매개 변수  
 `ot`  
 \[in\] 값을 지정의 [OBJECT\_TYPE](../../../extensibility/debugger/reference/object-type.md) 새 배열 개체의 형식을 나타내는 열거형입니다.  
  
 `pClassField`  
 \[in\] [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 인스턴스 값 개체의 배열을 만드는 경우 개체의 클래스를 나타내는 개체입니다.  기본 개체의 배열을 만드는 경우이 매개 변수는 null 값입니다.  
  
 `dwRank`  
 \[in\] 순위 또는 번호 배열입니다.  
  
 `dwDims`  
 \[in\] 배열의 각 차원의 크기입니다.  
  
 `dwLowBounds`  
 \[in\] 각 치수의 원점 \(일반적으로 0 또는 1\).  
  
 `ppObject`  
 \[out\] 반환 된 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 새로 만든된 배열을 나타내는 개체입니다.  실제로는 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md) 개체입니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 으로 표시 되며 함수는 배열 매개 변수를 나타내는 개체를 만드는 데이 메서드를 호출 하 여 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
## 참고 항목  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)
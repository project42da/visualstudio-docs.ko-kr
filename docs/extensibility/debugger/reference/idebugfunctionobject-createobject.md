---
title: "IDebugFunctionObject::CreateObject | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugFunctionObject::CreateObject"
helpviewer_keywords: 
  - "IDebugFunctionObject::CreateObject 메서드"
ms.assetid: c4c99dd5-609a-4e7c-8f29-eb728f57e995
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugFunctionObject::CreateObject
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

생성자를 사용 하 여 개체를 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT CreateObject(   
   IDebugFunctionObject* pConstructor,  
   DWORD                 dwArgs,  
   IDebugObject*         pArgs[],  
   IDebugObject**        ppObject  
);  
```  
  
```c#  
int CreateObject(  
   IDebugFunctionObject pConstructor,   
   uint                 dwArgs,   
   IDebugObject[]       pArgs,   
   out IDebugObject     ppObject  
);  
```  
  
#### 매개 변수  
 `pConstructor`  
 \[in\] [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 만들 개체의 생성자를 나타내는 개체입니다.  
  
 `dwArgs`  
 \[in\] 수의 매개 변수는 `pArg` 배열입니다.  생성자에 전달 된 매개 변수의 수를 나타냅니다.  
  
 `pArg`  
 \[in\] 배열 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 생성자에 전달 된 매개 변수를 나타내는 개체입니다.  
  
 `ppObject`  
 \[out\] 반환 된 `IDebugObject` , 새로 만들어진된 개체를 나타내는.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 클래스 \(또는 다른 복합 형식 생성자가 필요\)의 인스턴스를 나타내는 개체를 만드는 데이 메서드를 호출 즉 표시 되는 함수에 매개 변수를 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md) 인터페이스입니다.  
  
 생성자는 개체 매개 변수가 필요 하지 않습니다 경우 호출 하는 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md) 메서드.  
  
## 참고 항목  
 [IDebugFunctionObject](../../../extensibility/debugger/reference/idebugfunctionobject.md)   
 [CreateObjectNoConstructor](../../../extensibility/debugger/reference/idebugfunctionobject-createobjectnoconstructor.md)
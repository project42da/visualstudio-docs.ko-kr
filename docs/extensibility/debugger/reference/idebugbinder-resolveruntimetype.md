---
title: "IDebugBinder::ResolveRuntimeType | Microsoft Docs"
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
  - "IDebugBinder::ResolveRuntimeType"
helpviewer_keywords: 
  - "IDebugBinder::ResolveRuntimeType 메서드"
ms.assetid: 6456ab3e-1c03-4f3c-91f9-16797ab7f5e7
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugBinder::ResolveRuntimeType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 개체의 런타임 형식을 확인합니다.  
  
## 구문  
  
```cpp#  
HRESULT ResolveRuntimeType(   
   IDebugObject* pObject,  
   IDebugField** ppResolved  
);  
```  
  
```c#  
int ResolveRuntimeType(  
   IDebugObject     pObject,   
   out IDebugField  ppResolved  
);  
```  
  
#### 매개 변수  
 `pObject`  
 \[in\] [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md) 확인 되어야 합니다.  
  
 `ppResolved`  
 \[out\] 이름으로 개체의 형식을 반환 된 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md).  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 개체의 런타임 형식은 항상 컴파일 타임에 알 수 없습니다.  예를 들어, 다형성을 사용 하 여 인수를 함수에 단추 클래스와 같은 기본 클래스를 전달할 수 있습니다.  실제 인수 라디오 단추 클래스와 같은 파생된 클래스 수 있습니다.  
  
## 참고 항목  
 [IDebugBinder](../../../extensibility/debugger/reference/idebugbinder.md)   
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
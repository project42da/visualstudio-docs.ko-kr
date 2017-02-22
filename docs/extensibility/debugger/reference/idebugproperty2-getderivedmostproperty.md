---
title: "IDebugProperty2::GetDerivedMostProperty | Microsoft Docs"
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
  - "IDebugProperty2::GetDerivedMostProperty"
helpviewer_keywords: 
  - "IDebugProperty2::GetDerivedMostProperty"
ms.assetid: cc86b461-62d1-4340-8209-c65037fd8b02
caps.latest.revision: 9
caps.handback.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProperty2::GetDerivedMostProperty
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

파생 된 대부분 속성을의 속성을 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDerivedMostProperty (   
   IDebugProperty2** ppDerivedMost  
);  
```  
  
```c#  
int GetDerivedMostProperty (   
   out IDebugProperty2 ppDerivedMost  
);  
```  
  
#### 매개 변수  
 `ppDerivedMost`  
 \[out\] 반환 된 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 에서 대부분 파생 된 속성을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  반환 `S_GETDERIVEDMOST_NO_DERIVED_MOST` 없는 경우를 검색 하는 대부분 파생 된 속성입니다.  
  
## 설명  
 예를 들어,이 속성을 구현 하는 개체에 설명 합니다. `ClassRoot` 하지만 실제로의 인스턴스화 하는 `ClassDerived` 에서 파생 됩니다 `ClassRoot`,이 메서드를 반환 합니다는 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md) 개체를 설명 하는 `ClassDerived` 개체.  
  
## 참고 항목  
 [IDebugProperty2](../../../extensibility/debugger/reference/idebugproperty2.md)
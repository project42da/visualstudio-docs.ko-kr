---
title: "IDebugReference2::GetDerivedMostReference | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugReference2::GetDerivedMostReference"
helpviewer_keywords: 
  - "IDebugReference2::GetDerivedMostReference"
ms.assetid: 07253b74-7d39-48e0-8e85-ac8dfd919f6e
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugReference2::GetDerivedMostReference
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

대부분 파생 된 참조를 대 한 참조를 가져옵니다.  다음에 사용하도록 예약됩니다.  
  
## 구문  
  
```cpp#  
HRESULT GetDerivedMostReference(   
   IDebugReference2** ppDerivedMost  
);  
```  
  
```c#  
int GetDerivedMostReference(   
   out IDebugReference2 ppDerivedMost  
);  
```  
  
#### 매개 변수  
 `ppDerivedMost`  
 \[out\] 반환 된 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 에서 대부분 파생 된 속성을 나타내는 개체입니다.  
  
## 반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## 설명  
 예를 들어,이 속성을 구현 하는 개체에 설명 합니다. `ClassRoot` 하지만 실제로의 인스턴스화 하는 `ClassDerived` 에서 파생 된 `ClassRoot`,이 메서드를 반환 합니다는 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md) 에 대 한 참조를 나타내는 개체의 `ClassDerived` 개체.  
  
## 참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)
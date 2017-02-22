---
title: "IDebugArrayObject::GetRank | Microsoft Docs"
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
  - "IDebugArrayObject::GetRank"
helpviewer_keywords: 
  - "IDebugArrayObject::GetRank 메서드"
ms.assetid: 9948551a-e334-4ff6-979c-08dab633b9b6
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugArrayObject::GetRank
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

차수를 배열의 차원 수를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetRank(   
   DWORD* pdwRank  
);  
```  
  
```c#  
int GetRank(  
   out uint pdwRank  
);  
```  
  
#### 매개 변수  
 `pdwRank`  
 \[out\] 순위를 반환 합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용은 [GetDimensions](../../../extensibility/debugger/reference/idebugarrayobject-getdimensions.md) 메서드는 array 개체의 각 차원 크기를 검색할 수 있습니다.  
  
## 참고 항목  
 [IDebugArrayObject](../../../extensibility/debugger/reference/idebugarrayobject.md)
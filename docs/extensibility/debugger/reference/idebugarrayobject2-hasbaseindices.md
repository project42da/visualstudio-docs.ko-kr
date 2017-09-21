---
title: "IDebugArrayObject2::HasBaseIndices | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "HasBaseIndices"
  - "IDebugArrayObject2::HasBaseIndices"
ms.assetid: 51a5d145-ea53-422c-b5cf-c800cf64b8e6
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugArrayObject2::HasBaseIndices
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열에 기본 인덱스가 정의 \(경계값\) 사용 경우 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT HasBaseIndices (  
   BOOL* pfHasBaseIndices  
);  
```  
  
```c#  
int HasBaseIndices (  
   out bool pfHasBaseIndices  
);  
```  
  
#### 매개 변수  
 `pfHasBaseIndices`  
 \[out\] True 이면 배열 \(경계값\); 기본 인덱스가 지정 합니다 그렇지 않으면, FALSE입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.
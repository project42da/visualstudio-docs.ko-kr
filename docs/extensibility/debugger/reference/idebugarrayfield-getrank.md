---
title: "IDebugArrayField::GetRank | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugArrayField::GetRank"
helpviewer_keywords: 
  - "IDebugArrayField::GetRank 메서드"
ms.assetid: 2364b876-5be1-4bab-9b8f-3b6121da35c6
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugArrayField::GetRank
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

순위 또는 배열의 차원 수를 가져옵니다.  
  
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
 차수는 배열의 차원 수에 해당합니다.  C \+ \+ 및 C\#에서 다차원 배열의 실제 배열의 배열 되 고 따라서 단지 1 차원 배열로 간주 될 수 있습니다 \(및 해당 `GetRank` 메서드는 항상 1 반환\).  [!INCLUDE[vbprvb](../../../code-quality/includes/vbprvb_md.md)], 반면, 다차원 배열 다르게 처리 및 이러한 배열의 차원 수를 반영 \(와 `GetRank` 메서드는 항상 차원 수를 반환\)입니다.  
  
## 참고 항목  
 [IDebugArrayField](../../../extensibility/debugger/reference/idebugarrayfield.md)
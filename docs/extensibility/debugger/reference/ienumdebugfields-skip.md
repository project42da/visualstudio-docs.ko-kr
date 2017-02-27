---
title: "IEnumDebugFields::Skip | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugFields::Skip"
helpviewer_keywords: 
  - "IEnumDebugFields::Skip 메서드"
ms.assetid: b3bc51c4-21ae-4913-800c-c2ca9dc18443
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IEnumDebugFields::Skip
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 방법을 통해 지정한 수의 요소를 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip(  
   ULONG celt  
);  
```  
  
```c#  
int Skip(  
   uint celt  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 건너뛸 요소의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 경우 `celt` 나머지 요소; 개수 보다 큽니다 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 경우 `celt` 숫자 보다 큰 값을 지정 합니다. 나머지 요소를 열거형을 끝으로 설정 됩니다 및 `S_FALSE` 이 반환 됩니다.  
  
## 참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)
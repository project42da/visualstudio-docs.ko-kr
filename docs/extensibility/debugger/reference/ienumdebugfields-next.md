---
title: "IEnumDebugFields::Next | Microsoft Docs"
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
  - "IEnumDebugFields::Next"
helpviewer_keywords: 
  - "IEnumDebugFields::Next 메서드"
ms.assetid: 22c177a2-af81-4234-812b-f9b47be245a2
caps.latest.revision: 7
caps.handback.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugFields::Next
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 요소는 다음 집합 열거에서 반환 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT Next(  
   ULONG         celt,  
   IDebugField** rgelt,  
   ULONG*        pceltFetched  
);  
```  
  
```c#  
int Next(  
   uint          celt,  
   IDebugField[] rgelt,  
   ref uint      pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 검색할 요소의 수입니다.  도의 최대 크기를 지정은 `rgelt` 배열입니다.  
  
 `rgelt`  
 \[in, out\] 배열 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md) 요소를 채울 수 있도록 합니다.  
  
 `pceltFetched`  
 \[out\] 실제로 반환 된 요소 수를 반환 합니다. `rgelt`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 미만인 경우 요청 된 수의 요소를 반환할 수 없습니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IEnumDebugFields](../../../extensibility/debugger/reference/ienumdebugfields.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)
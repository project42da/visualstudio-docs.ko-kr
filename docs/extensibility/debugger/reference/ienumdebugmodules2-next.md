---
title: "IEnumDebugModules2::Next | Microsoft Docs"
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
  - "IEnumDebugModules2::Next"
helpviewer_keywords: 
  - "IEnumDebugModules2::Next"
ms.assetid: 46b7ccad-b07b-4ec0-b3ce-13981ffab7e8
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugModules2::Next
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

열거형의 다음 집합의 요소를 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next(  
   ULONG           celt,  
   IDebugModule2** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
```c#  
int Next(  
   uint            celt,  
   IDebugModule2[] rgelt,  
   ref uint        pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 검색할 요소의 수입니다.  도의 최대 크기를 지정은 `rgelt` 배열입니다.  
  
 `rgelt`  
 \[in, out\] 배열 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md) 요소를 채울 수 있도록 합니다.  
  
 `pceltFetched`  
 \[out\] 실제로 반환 된 요소 수를 반환 합니다. `rgelt`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 미만인 경우 요청 된 수의 요소를 반환할 수 없습니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)   
 [IDebugModule2](../../../extensibility/debugger/reference/idebugmodule2.md)
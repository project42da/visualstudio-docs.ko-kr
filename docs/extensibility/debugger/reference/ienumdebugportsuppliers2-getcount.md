---
title: "IEnumDebugPortSuppliers2::GetCount | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugPortSuppliers2::GetCount"
helpviewer_keywords: 
  - "IEnumDebugPortSuppliers2::GetCount"
ms.assetid: 004f78dd-87d0-41a8-bcaa-f7fadbfeb8fc
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IEnumDebugPortSuppliers2::GetCount
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

열거형의 요소 수를 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT GetCount(  
   ULONG* pcelt  
);  
```  
  
```c#  
int GetCount(  
   out uint pcelt  
);  
```  
  
#### 매개 변수  
 `pcelt`  
 \[out\] 열거형의 요소 수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 사용할 수 없습니다. 지정만 일반적인 COM 열거형 인터페이스는 `Next`, `Clone`, `Skip`, 및 `Reset` 메서드 구현 해야.  
  
## 참고 항목  
 [IEnumDebugPortSuppliers2](../../../extensibility/debugger/reference/ienumdebugportsuppliers2.md)
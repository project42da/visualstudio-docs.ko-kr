---
title: "IDebugObject::IsReadOnly | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject::IsReadOnly"
helpviewer_keywords: 
  - "IDebugObject::IsReadOnly 메서드"
ms.assetid: c460f772-d08a-4b36-81f3-dff6a51a93fd
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugObject::IsReadOnly
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 개체가 읽기 전용인 지 여부를 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsReadOnly(   
   BOOL* pfIsReadOnly  
);  
```  
  
```c#  
int IsReadOnly(  
   out int pfIsReadOnly  
);  
```  
  
#### 매개 변수  
 `pfIsReadOnly`  
 \[out\] 0이 아닌 반환 \(`TRUE`\) 이면이 개체가 읽기 전용입니다. 그렇지 않은 경우 0을 반환 \(`FALSE`\).  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 읽기 전용 개체 만든 후 변경 하는 값을 가질 수 없습니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)
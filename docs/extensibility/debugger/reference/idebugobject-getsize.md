---
title: "IDebugObject::GetSize | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugObject::GetSize"
helpviewer_keywords: 
  - "IDebugObject::GetSize 메서드"
ms.assetid: 89af423b-36eb-479d-b2de-2693455eca15
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IDebugObject::GetSize
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

개체의 크기를 \(바이트\)를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetSize(   
   UINT* pnSize  
);  
```  
  
```c#  
int GetSize(  
   out uint pnSize  
);  
```  
  
#### 매개 변수  
 `pnSize`  
 \[out\] 크기 \(바이트\)를 반환합니다.  
  
## 반환 값  
 성공 하면 S\_OK를 반환 합니다. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 사용은 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md) 바이트 시퀀스로 값을 검색 하는 방법입니다.  
  
## 참고 항목  
 [IDebugObject](../../../extensibility/debugger/reference/idebugobject.md)   
 [GetValue](../../../extensibility/debugger/reference/idebugobject-getvalue.md)
---
title: "IDebugField::GetKind | Microsoft Docs"
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
  - "IDebugField::GetKind"
helpviewer_keywords: 
  - "IDebugField::GetKind 메서드"
ms.assetid: e7c9c60a-8e55-4ecc-aa63-0c814a1e92cc
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugField::GetKind
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 필드의 종류를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetKind(   
   FIELD_KIND* pdwKind  
);  
```  
  
```c#  
int GetKind(  
   out enum_FIELD_KIND pdwKind  
);  
```  
  
#### 매개 변수  
 `pdwKind`  
 \[out\] 종류 필드의 조합으로 반환 [FIELD\_KIND](../../../extensibility/debugger/reference/field-kind.md) 상수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD\_KIND](../../../extensibility/debugger/reference/field-kind.md)
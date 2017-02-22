---
title: "IDebugReference2::SetReferenceType | Microsoft Docs"
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
  - "IDebugReference2::SetReferenceType"
helpviewer_keywords: 
  - "IDebugReference2::SetReferenceType"
ms.assetid: 5854a172-ea82-481c-97d9-c7fc16923d44
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugReference2::SetReferenceType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

참조 형식을 설정합니다.  다음에 사용하도록 예약됩니다.  
  
## 구문  
  
```cpp#  
HRESULT SetReferenceType (   
   REFERENCE_TYPE dwRefType  
);  
```  
  
```c#  
int SetReferenceType (   
   enum_REFERENCE_TYPE dwRefType  
);  
```  
  
#### 매개 변수  
 `dwRefType`  
 \[in\] 값은 [REFERENCE\_TYPE](../../../extensibility/debugger/reference/reference-type.md) 참조 유형을 지정 하는 열거형입니다.  
  
## 반환 값  
 항상 `E_NOTIMPL`를 반환합니다.  
  
## 참고 항목  
 [IDebugReference2](../../../extensibility/debugger/reference/idebugreference2.md)   
 [REFERENCE\_TYPE](../../../extensibility/debugger/reference/reference-type.md)
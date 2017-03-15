---
title: "IDebugExtendedField::IsClosedType | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "IsClosedType"
  - "IDebugExtendedField::IsClosedType"
ms.assetid: 9136fc57-74ff-4fe4-a6e2-b137cb9d5b08
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugExtendedField::IsClosedType
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

닫힌된 형식 필드를 나타내는지 여부를 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT IsClosedType(  
   void  
);  
```  
  
```c#  
int IsClosedType();  
```  
  
## 반환 값  
 닫힌된 형식 필드인 경우, 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE`.  
  
## 참고 항목  
 [IDebugExtendedField](../../../extensibility/debugger/reference/idebugextendedfield.md)
---
title: "IDebugField::GetTypeInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugField::GetTypeInfo"
helpviewer_keywords: 
  - "IDebugField::GetTypeInfo 메서드"
ms.assetid: bb5acfa3-04c3-4088-be84-9ff8926cd16f
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugField::GetTypeInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 기호 또는 형식에 대 한 형식에 관계 없이 정보를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetTypeInfo(   
   TYPE_INFO* pTypeInfo  
);  
```  
  
```c#  
int GetTypeInfo(  
   TYPE_INFO[] pTypeInfo  
);  
```  
  
#### 매개 변수  
 `pTypeInfo`  
 \[out\] 유형을 반환 정보에 제공 된 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md) 구조체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 형식에 관계 없이 정보 예를 들어, AppDomain, 모듈 및 기호를 포함 하는 클래스에 포함 됩니다.  
  
## 참고 항목  
 [GetType](../../../extensibility/debugger/reference/idebugfield-gettype.md)   
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [TYPE\_INFO](../../../extensibility/debugger/reference/type-info.md)
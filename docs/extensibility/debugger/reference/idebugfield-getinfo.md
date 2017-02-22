---
title: "IDebugField::GetInfo | Microsoft Docs"
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
  - "IDebugField::GetInfo"
helpviewer_keywords: 
  - "IDebugField::GetInfo 메서드"
ms.assetid: 7d508200-89ce-400f-a8ea-f28e7610cb2b
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugField::GetInfo
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 메서드는 필드에 대 한 정보를 표시할 수를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetInfo(   
   FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO* pFieldInfo  
);  
```  
  
```c#  
int GetInfo(  
   enum_FIELD_INFO_FIELDS dwFields,  
   FIELD_INFO[] pFieldInfo  
);  
```  
  
#### 매개 변수  
 `dwFields`  
 \[in\] 함께 [FIELD\_INFO\_FIELDS](../../../extensibility/debugger/reference/field-info-fields.md) 표시할 정보를 선택 하는 상수입니다.  필드에 기호를 나타내는 경우 일반적으로 심볼 이름 및 형식입니다.  
  
 `pFieldInfo`  
 \[out\] 제공 된 정보를 반환 합니다. [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md) 구조체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugField](../../../extensibility/debugger/reference/idebugfield.md)   
 [FIELD\_INFO](../../../extensibility/debugger/reference/field-info.md)
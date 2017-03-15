---
title: "METADATA_ADDRESS_FIELD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "METADATA_ADDRESS_FIELD"
helpviewer_keywords: 
  - "METADATA_ADDRESS_FIELD 구조"
ms.assetid: 15ab45fe-6b3b-4e09-880b-31b34f523607
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# METADATA_ADDRESS_FIELD
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조체의 필드는 클래스 또는 구조체의 주소를 나타냅니다.  
  
## 구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_FIELD {  
   _mdToken tokField;  
} METADATA_ADDRESS_FIELD  
```  
  
```c#  
public struct METADATA_ADDRESS_FIELD {  
   public int tokField;  
}  
```  
  
## 용어  
 tokField  
 필드 토큰의 ID입니다.  
  
 \[C\+\+\] `_mdToken` is a `typedef` for a 32\-bit `int`.  
  
## 설명  
 이 구조 연합에 속하지는 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 때 구조는 `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 구조 설정 되어 `ADDRESS_KIND_FIELD` \(값의 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형\).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md)
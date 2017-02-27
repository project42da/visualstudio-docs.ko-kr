---
title: "METADATA_ADDRESS_ARRAYELEM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "METADATA_ADDRESS_ARRAYELEM"
helpviewer_keywords: 
  - "METADATA_ADDRESS_ARRAYELEM 구조"
ms.assetid: 24321be5-7c17-4038-82a1-c20a2b68ff3c
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# METADATA_ADDRESS_ARRAYELEM
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

배열 요소를 배열 내에서이 구조체를 나타냅니다.  
  
## 구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_ARRAYELEM {  
   _mdToken tokMethod;  
   DWORD    dwIndex;  
} METADATA_ADDRESS_ARRAYELEM;  
```  
  
```c#  
public struct METADATA_ADDRESS_ARRAYELEM {  
   public int  tokMethod;  
   public uint dwIndex;  
}  
```  
  
## 용어  
 tokMethod  
 배열 ID이이 요소 부분입니다.  
  
 \[C\+\+\] `_mdToken` is a `typedef` for a 32\-bit `int`.  
  
 dwIndex  
 이 배열 내에서 요소의 인덱스입니다.  
  
## 설명  
 이 구조 연합에 속하지는 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 때 구조는 `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 구조 설정 되어 `ADDRESS_KIND_ARRAYELEM` \(값의 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형\).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md)
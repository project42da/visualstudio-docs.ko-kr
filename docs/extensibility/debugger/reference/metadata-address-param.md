---
title: "METADATA_ADDRESS_PARAM | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "METADATA_ADDRESS_PARAM"
helpviewer_keywords: 
  - "METADATA_ADDRESS_PARAM 구조"
ms.assetid: 90904f19-0e71-4cb3-a56e-6a2e92f66dfc
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# METADATA_ADDRESS_PARAM
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조체는 메서드 또는 함수의 매개 변수를 나타냅니다.  
  
## 구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_PARAM {  
   _mdToken tokMethod;  
   _mdToken tokParam;  
   DWORD    dwIndex;  
} METADATA_ADDRESS_PARAM;  
```  
  
```c#  
public struct METADATA_ADDRESS_PARAM {  
   public int  tokMethod;  
   public int  tokParam;  
   public uint dwIndex;  
}  
```  
  
## 용어  
 tokMethod  
 메서드는 ID 매개 변수 부분입니다.  
  
 tokParam  
 매개 변수의 ID입니다.  
  
 dwIndex  
 매개 변수 목록에서 매개 변수의 인덱스입니다.  
  
## 설명  
 이 구조 연합에 속하지는 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 때 구조는 `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 구조 설정 되어 `ADDRESS_KIND_PARAM` \(값의 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형\).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md)
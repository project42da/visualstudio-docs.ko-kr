---
title: "METADATA_ADDRESS_METHOD | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "METADATA_ADDRESS_METHOD"
helpviewer_keywords: 
  - "METADATA_ADDRESS_METHOD 구조"
ms.assetid: fc0e5370-1b4f-4867-837f-0d63c4b9dd09
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# METADATA_ADDRESS_METHOD
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조는 주소를 클래스의 메서드를 나타냅니다.  
  
## 구문  
  
```cpp  
typedef struct _tagMETADATA_ADDRESS_METHOD {  
   _mdToken tokMethod;  
   DWORD    dwOffset;  
   DWORD    dwVersion;  
} METADATA_ADDRESS_METHOD;  
```  
  
```c#  
public struct METADATA_ADDRESS_METHOD {  
   public int  tokMethod;  
   public uint dwOffset;  
   public uint dwVersion;  
}  
```  
  
## 용어  
 tokMethod  
 메서드 ID입니다.  
  
 \[C\+\+\] `_mdToken` is a `typedef` for a 32\-bit `int`.  
  
 dwOffset  
 \(오프셋에 vtable을 나타낼 수 있습니다.\)이 메서드가 클래스의 시작 까지의 오프셋입니다.  
  
 dwVersion  
 \(이 값은 기호 공급자에 게 고유\) 메서드 버전입니다.  
  
## 설명  
 이 구조 연합에 속하지는 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 때 구조는 `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 구조 설정 되어 `ADDRESS_KIND_METHOD` \(값의 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형\).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)   
 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md)
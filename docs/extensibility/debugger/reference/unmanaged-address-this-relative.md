---
title: "UNMANAGED_ADDRESS_THIS_RELATIVE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "UNMANAGED_ADDRESS_THIS_RELATIVE"
helpviewer_keywords: 
  - "UNMANAGED_ADDRESS_THIS_RELATIVE 구조"
ms.assetid: e6a91ace-2d47-4ff9-aefb-8d8b68eab0b2
caps.latest.revision: 6
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 6
---
# UNMANAGED_ADDRESS_THIS_RELATIVE
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 구조를 기준으로 주소를 나타내는 있는 `this` 포인터 \(`Me` Visual Basic\).  
  
## 구문  
  
```cpp  
typedef struct _tagUNMANAGED_THIS_RELATIVE {  
   DWORD dwOffset;  
   DWORD dwBitOffset;  
   DWORD dwBitLength;  
} UNMANAGED_ADDRESS_THIS_RELATIVE;  
```  
  
```c#  
public struct UNMANAGED_THIS_RELATIVE {  
   public uint dwOffset;  
   public uint dwBitOffset;  
   public uint dwBitLength;  
}  
```  
  
## 용어  
 dwOffset  
 바이트의 기본 위치 \(예: 클래스 vtable의 시작\)에서 오프셋입니다.  
  
 dwBitOffset  
 기본 위치에서 비트에서 오프셋 \(항상 0 비트 필드를 참조 하는 경우를 제외\).  
  
 dwBitLength  
 주소를 나타내는 비트 수 \(항상 0 비트 필드를 참조 하는 경우를 제외\).  
  
## 설명  
 이 구조 연합에 속하지는 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md) 때 구조는 `dwKind` 필드는 `DEBUG_ADDRESS_UNION` 구조 설정 되어 `ADDRESS_KIND_UNMANAGED_THIS_RELATIVE` \(값의 [ADDRESS\_KIND](../../../extensibility/debugger/reference/address-kind.md) 열거형\).  
  
## 요구 사항  
 헤더: sh.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [구조체 및 공용 구조체](../../../extensibility/debugger/reference/structures-and-unions.md)   
 [DEBUG\_ADDRESS\_UNION](../../../extensibility/debugger/reference/debug-address-union.md)
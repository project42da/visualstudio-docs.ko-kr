---
title: "UdtKind | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "UdtKind 열거형"
ms.assetid: 400b59b9-373c-42cb-aae1-570494214328
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# UdtKind
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

다양 한 사용자 정의 형식 \(UDT\)에 대해 설명 합니다.  
  
## 구문  
  
```cpp#  
enum UdtKind {   
   UdtStruct,  
   UdtClass,  
   UdtUnion,  
   UdtInterface  
};  
```  
  
## Elements  
 UdtStruct  
 UDT는 구조입니다.  
  
 UdtClass  
 UDT는 클래스입니다.  
  
 UdtUnion  
 UDT는 공용 구조체입니다.  
  
 UdtInterface  
 UDT는 인터페이스입니다.  
  
## 설명  
 이 열거형의 값으로 반환 되는 [IDiaSymbol::get\_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md) 메서드.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_udtKind](../../debugger/debug-interface-access/idiasymbol-get-udtkind.md)
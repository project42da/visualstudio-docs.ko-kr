---
title: "THUNK_ORDINAL | Microsoft Docs"
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
  - "Thunk_Ordinal 열거형"
ms.assetid: 026f98a9-36b8-41ef-8a72-12d7cbc2d362
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# THUNK_ORDINAL
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

썽크 형식을 지정합니다.  
  
## 구문  
  
```cpp#  
typedef enum THUNK_ORDINAL {   
   THUNK_ORDINAL_NOTYPE,  
   THUNK_ORDINAL_ADJUSTOR,  
   THUNK_ORDINAL_VCALL,  
   THUNK_ORDINAL_PCODE,  
   THUNK_ORDINAL_LOAD   
  
   // trampoline thunk ordinals - only for use in Trampoline thunk symbols  
   THUNK_ORDINAL_TRAMP_INCREMENTAL,  
   THUNK_ORDINAL_TRAMP_BRANCHISLAND,  
} THUNK_ORDINAL;  
```  
  
## Elements  
 THUNK\_ORDINAL\_NOTYPE  
 표준 만들어집니다.  
  
 THUNK\_ORDINAL\_ADJUSTOR  
 A `this` 조정기 만들어집니다.  
  
 THUNK\_ORDINAL\_VCALL  
 가상 호출 썽크입니다.  
  
 THUNK\_ORDINAL\_PCODE  
 P\-코드를 썽크.  
  
 THUNK\_ORDINAL\_LOAD  
 지연 로드 썽크로 제어 합니다.  
  
 THUNK\_ORDINAL\_TRAMP\_INCREMENTAL  
 증분 trampoline 썽크 \(trampoline 썽크 메모리 공간에서 다른 호출을 반송 하 사용\).  
  
 THUNK\_ORDINAL\_TRAMP\_BRANCHISLAND  
 분기 지점 trampoline 만들어집니다.  
  
## 설명  
 이 열거형에 있는 값에 대 한 호출에서 반환 되는 [IDiaSymbol::get\_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md) 메서드가 있습니다.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_thunkOrdinal](../../debugger/debug-interface-access/idiasymbol-get-thunkordinal.md)
---
title: "IDiaSymbol::get_subType | Microsoft Docs"
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
ms.assetid: 0b3cbf77-8f11-434a-ad60-ea9829fec6fa
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_subType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

하위 형식을 검색합니다.  
  
## 구문  
  
```cpp  
HRESULT get_subType(   
   IDiaSymbol** pRetVal);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 하위 형식에 대 한 포인터입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
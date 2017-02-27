---
title: "IDiaSymbol::get_numberOfRows | Microsoft Docs"
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
ms.assetid: cf3eb110-d07f-4995-b68b-08290aa67d6f
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_numberOfRows
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

행렬의 행 수를 검색합니다.  
  
## 구문  
  
```cpp  
HRESULT get_numberOfRows(   
   DWORD* pRetVal);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 에 대 한 포인터는 `DWORD` 행렬의 행 수를 포함 합니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: "IDiaSegment::get_write | Microsoft Docs"
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
  - "IDiaSegment::get_write 메서드"
ms.assetid: 5fcda988-6be1-4b2f-8660-b59aa78fc35d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSegment::get_write
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

세그먼트를 수정할 수 있는지 여부를 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_write (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 세그먼트에; 쓸 수 있는 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
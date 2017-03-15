---
title: "IDiaSectionContrib::get_remove | Microsoft Docs"
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
  - "IDiaSectionContrib::get_remove 메서드"
ms.assetid: fd30ab7b-022b-4402-a42a-2d38e274c1b1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSectionContrib::get_remove
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

섹션에 메모리에 이미지 부분 전에 제거할지 여부를 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_remove (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 섹션; 메모리에 이미지를 추가할 수 없는 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
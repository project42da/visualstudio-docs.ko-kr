---
title: "IDiaSectionContrib::get_code16bit | Microsoft Docs"
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
  - "IDiaSectionContrib::get_code16bit 메서드"
ms.assetid: 8cde8fc5-9546-4f82-b4a8-afd0d835039e
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSectionContrib::get_code16bit
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

16 비트 코드 섹션이 있는지 여부를 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_code16bit(  
   BOOL *pRetVal  
};  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 경우 코드 섹션에서 16 비트입니다. 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드는 코드 16 비트 임을 나타냅니다.  코드가 없습니다 16 비트 이면 32 비트 또는 64 비트 코드와 같은 다른 수 있습니다.  
  
## 참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
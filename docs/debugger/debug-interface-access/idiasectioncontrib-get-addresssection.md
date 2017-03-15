---
title: "IDiaSectionContrib::get_addressSection | Microsoft Docs"
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
  - "IDiaSectionContrib::get_addressSection 메서드"
ms.assetid: 13fe7e0b-c978-4a1d-bb57-64c8583b5e14
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSectionContrib::get_addressSection
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기여의 주소 구역 부분을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_addressSection (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 구역 일부에 대 한 기여도 주소를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
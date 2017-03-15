---
title: "IDiaEnumSegments::get_Count | Microsoft Docs"
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
  - "IDiaEnumSegments::get_Count 메서드"
ms.assetid: c62a0fda-17b8-4cf6-b321-6014ce581096
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSegments::get_Count
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

세그먼트의 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_Count (   
   LONG* pRetVal  
);  
```  
  
#### 매개 변수  
 pRetVal  
 \[out, retval\] 세그먼트의 수를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaEnumSegments::Item](../../debugger/debug-interface-access/idiaenumsegments-item.md)
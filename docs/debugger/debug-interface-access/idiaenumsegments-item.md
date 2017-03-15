---
title: "IDiaEnumSegments::Item | Microsoft Docs"
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
  - "IDiaEnumSegments::Item 메서드"
ms.assetid: ee44dd55-39a0-4b7b-97ff-2e1226eeb2bd
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSegments::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

세그먼트의 인덱스를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   DWORD         index,  
   IDiaSegment** segment  
);  
```  
  
#### 매개 변수  
 인덱스\(index\)  
 \[in\] 색인은 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 검색할 개체입니다.  인덱스는 범위가 0입니다 `count`\-1, 어디 `count` 반환 하는 있는 [IDiaEnumSegments::get\_Count](../../debugger/debug-interface-access/idiaenumsegments-get-count.md) 메서드.  
  
 세그먼트\(segment\)  
 \[out\] 반환 된 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 원하는 세그먼트를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
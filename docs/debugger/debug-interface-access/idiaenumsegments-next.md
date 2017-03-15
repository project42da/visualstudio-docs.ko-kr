---
title: "IDiaEnumSegments::Next | Microsoft Docs"
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
  - "IDiaEnumSegments::Next 메서드"
ms.assetid: 53f61874-d821-47ab-a1f5-27e982804a6a
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSegments::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

세그먼트 열거 시퀀스에서 지정 된 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next (   
   ULONG         celt,   
   IDiaSegment** rgelt,  
   ULONG*        pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 검색할 열거자에 세그먼트의 수입니다.  
  
 rgelt  
 \[out\] 원하는 항목으로 채울 수 있도록 되어 있는 배열 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md) 세그먼트를 나타내는 개체입니다.  
  
 pceltFetched  
 \[out\] 세그먼트에서 반입 된 열거자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 있는 경우 더 많은 세그먼트가 없습니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)   
 [IDiaSegment](../../debugger/debug-interface-access/idiasegment.md)
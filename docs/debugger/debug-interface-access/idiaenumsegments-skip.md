---
title: "IDiaEnumSegments::Skip | Microsoft Docs"
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
  - "IDiaEnumSegments::Skip 메서드"
ms.assetid: ec67039f-da8c-4e70-8db7-957d7d5281e8
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSegments::Skip
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

세그먼트 열거 시퀀스에서 지정 된 수를 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 열거형 시퀀스를 건너뛸 세그먼트의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 있는 경우 더 많은 세그먼트가 건너뛸 수 없습니다.  
  
## 참고 항목  
 [IDiaEnumSegments](../../debugger/debug-interface-access/idiaenumsegments.md)
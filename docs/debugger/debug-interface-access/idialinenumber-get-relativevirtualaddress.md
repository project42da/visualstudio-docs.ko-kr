---
title: "IDiaLineNumber::get_relativeVirtualAddress | Microsoft Docs"
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
  - "IDiaLineNumber::get_relativeVirtualAddress 메서드"
ms.assetid: ba8142e3-5c77-43cc-bd33-c077dcc18cab
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaLineNumber::get_relativeVirtualAddress
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

블록의 상대 가상 주소 \(RVA\)를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_relativeVirtualAddress (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 블록 이미지 상대 가상 주소를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
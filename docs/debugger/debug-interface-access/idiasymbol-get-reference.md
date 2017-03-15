---
title: "IDiaSymbol::get_reference | Microsoft Docs"
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
  - "IDiaSymbol::get_reference 메서드"
ms.assetid: 6a97cb74-6a14-41fd-8e24-2a42d7a1e529
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_reference
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

포인터 형식에 대 한 참조 인지 여부를 지정 하는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_reference (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 경우 포인터 형식에 대 한 참조입니다. 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
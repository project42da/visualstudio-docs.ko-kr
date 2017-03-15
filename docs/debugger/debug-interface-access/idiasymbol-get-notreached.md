---
title: "IDiaSymbol::get_notReached | Microsoft Docs"
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
  - "IDiaSymbol::get_notReached 메서드"
ms.assetid: e44ba922-6cda-40c2-9b62-44e5a8628e63
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_notReached
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

함수 또는 레이블 절대로 도달할 수 있는지 여부를 지정 하는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_notReached(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 pFlag  
 \[out\] 반환 `TRUE` 함수 또는 레이블 도달할 경우. 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
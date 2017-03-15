---
title: "IDiaSymbol::get_isAggregated | Microsoft Docs"
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
  - "IDiaSymbol::get_isAggregated 메서드"
ms.assetid: 24d280ef-6ea3-4958-9418-4ad3ca7c67c1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_isAggregated
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 기호 집계 또는 심볼의 컬렉션의 일부 인지 여부를 지정 하는 플래그를 검색 합니다. 컴파일러 집계 된 기호를 별도 엔터티로 취급 합니다 있지만 정말 하나의 큰 심볼의 일부입니다.  
  
## 구문  
  
```cpp#  
HRESULT get_isAggregated(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 데이터의 분할에서 부모 기호; 기호 집계에 포함 된 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 [IDiaSymbol::get\_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md) 메서드는 `TRUE` 부모 집계 된 기호를 기호에 대 한.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get\_isSplitted](../../debugger/debug-interface-access/idiasymbol-get-issplitted.md)
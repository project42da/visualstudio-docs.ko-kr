---
title: "IDiaSymbol::get_hasAlloca | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol::get_hasAlloca 메서드"
ms.assetid: 3b9fb747-670b-4da7-bb70-612f7b911786
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_hasAlloca
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 함수 호출이 포함 되어 있는지 여부를 지정 하는 플래그를 검색 `alloca` \(사용 스택에 메모리를 할당할 수\).  
  
## 구문  
  
```  
[C++]HRESULT get_hasAlloca(   BOOL *pFlag);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 를 호출 하는 함수를 포함 하는 경우 `alloca`. 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
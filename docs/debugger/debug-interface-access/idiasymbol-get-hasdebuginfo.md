---
title: "IDiaSymbol::get_hasDebugInfo | Microsoft Docs"
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
  - "IDiaSymbol::get_hasDebugInfo 메서드"
ms.assetid: 84cd2b67-0d83-4589-9ecb-a4bcbeed55f5
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_hasDebugInfo
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 하는 플래그를 검색은 [컴파일 대상](../../debugger/debug-interface-access/compiland.md) 디버깅 정보를 포함 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_hasDebugInfo(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 경우 컴파일 대상 디버깅 정보입니다. 그렇지 않으면 반환 `FALSE`.  
  
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
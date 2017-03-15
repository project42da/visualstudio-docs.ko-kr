---
title: "IDiaSymbol::get_optimizedCodeDebugInfo | Microsoft Docs"
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
  - "IDiaSymbol::get_optimizedCodeDebugInfo 메서드"
ms.assetid: 57ef4170-37a9-46b0-8217-c1a674725113
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSymbol::get_optimizedCodeDebugInfo
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

함수는 최적화 된 코드에 대 한 특정 정보가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_optimizedCodeDebugInfo(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 최적화된 함수 또는 레이블에 디버깅 정보가 포함되면 `TRUE`를 반환하고, 그렇지 않으면 `FALSE`를 반환합니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
> [!NOTE]
>  `S_FALSE` 반환 값은 속성을 기호에 사용할 수 없음을 의미합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|헤더:|dia2.h|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
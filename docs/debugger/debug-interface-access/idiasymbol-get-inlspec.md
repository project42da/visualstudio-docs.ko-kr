---
title: "IDiaSymbol::get_InlSpec | Microsoft Docs"
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
  - "IDiaSymbol::get_InlSpec 메서드"
ms.assetid: 30af6a2f-be84-429e-a96a-d0f9ed9343fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_InlSpec
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 함수는 함수 인라인으로 표시 되어 있는지 여부를 나타내는 플래그를 검색 \(중 하나를 사용 하는 [inline, \_\_inline, \_\_forceinline](../../misc/inline-inline-forceinline.md) 속성\).  
  
## 구문  
  
```cpp#  
HRESULT get_inlSpec(  
   BOOL *pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 함수는 인라인;로 표시 되어 있으면 그렇지 않으면 반환 `FALSE`.  
  
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
 [inline, \_\_inline, \_\_forceinline](../../misc/inline-inline-forceinline.md)
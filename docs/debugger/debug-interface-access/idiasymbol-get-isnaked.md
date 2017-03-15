---
title: "IDiaSymbol::get_isNaked | Microsoft Docs"
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
  - "IDiaSymbol::get_isNaked 메서드"
ms.assetid: b16629dc-8e17-476b-9c7b-58e7277c61ed
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_isNaked
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

함수가 있는지 여부를 지정 하는 플래그를 검색은 [naked](/visual-cpp/cpp/naked-cpp) 특성 \(즉, 함수 프롤로그 나 에필로그 코드 컴파일러에 의해 추가 했습니다\).  
  
## 구문  
  
```cpp  
HRESULT get_isNaked(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 경우이 함수는 `naked` 특성입니다. 그렇지 않으면 반환 `FALSE`.  
  
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
 [Naked 함수 호출](/visual-cpp/cpp/naked-function-calls)
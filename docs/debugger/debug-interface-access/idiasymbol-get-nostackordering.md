---
title: "IDiaSymbol::get_noStackOrdering | Microsoft Docs"
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
  - "IDiaSymbol::get_noStackOrdering 메서드"
ms.assetid: a1753917-705b-4165-9880-d05e91e6dcb4
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_noStackOrdering
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 함수는 스택 순서 지정 스택 버퍼 검사의 일환으로 수행할 수 있는지 여부를 나타내는 플래그를 가져옵니다 \([\/GS\(버퍼 보안 검사\)](/visual-cpp/build/reference/gs-buffer-security-check) 컴파일러 옵션을\).  
  
## 구문  
  
```cpp#  
HRESULT get_noStackOrdering(  
   BOOL *pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 스택 순서 지정 스택 버퍼 검사;의 일환으로 하면 그렇지 않으면 반환 `FALSE`.  
  
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
 [\/GS\(버퍼 보안 검사\)](/visual-cpp/build/reference/gs-buffer-security-check)
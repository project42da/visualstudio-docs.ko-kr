---
title: "IDiaSymbol::get_hasEHa | Microsoft Docs"
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
  - "IDiaSymbol::get_hasEHa 메서드"
ms.assetid: cb61dfd9-fe69-461c-8185-288440454864
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_hasEHa
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

비동기 \(구조적된\) 예외 처리 함수를 포함 하는지 여부를 지정 하는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_hasEHa(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 경우 함수는 비동기 예외 처리 됩니다. 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 설명  
 비동기 또는 구조적 예외 처리와 스타일 C\+\+ 예외 처리를 함께 사용할 수 있지만 특정 컴파일러 스위치를 사용 하려면 \/eha를 필요로 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: "IDiaSymbol::get_indirectVirtualBaseClass | Microsoft Docs"
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
  - "IDiaSymbol::get_indirectVirtualBaseClass 메서드"
ms.assetid: 853b5c6f-e1cb-4675-ad36-9ee16e3341c3
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_indirectVirtualBaseClass
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 정의 데이터 형식을 간접 가상 기본 클래스 인지 여부를 지정 하는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_indirectVirtualBaseClass (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 간접 가상 기본 클래스입니다; 사용자 정의 데이터 형식인 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 7.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
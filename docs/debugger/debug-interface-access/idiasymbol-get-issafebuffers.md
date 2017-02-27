---
title: "IDiaSymbol::get_isSafeBuffers | Microsoft Docs"
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
  - "IDiaSymbol::get_isSafeBuffers 메서드"
ms.assetid: f29e373d-e7bb-4181-ab9f-bf708d401d83
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IDiaSymbol::get_isSafeBuffers
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

수신 버퍼에 대 한 preprocesser 지시문 사용 여부를 지정 하는 플래그를 검색 합니다.  사용 하는 경우는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 으로 설정 `SymTagFunction`.  
  
## 구문  
  
```cpp#  
HRESULT get_isSafeBuffers(   
   BOOL* pRetVal)  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 포인터가 안전 버퍼를; 전처리기 지시문을 사용 하는 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [strict\_gs\_check](/visual-cpp/preprocessor/strict-gs-check)
---
title: "IDiaSymbol::get_sealed | Microsoft Docs"
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
  - "IDiaSymbol::get_sealed 메서드"
ms.assetid: cd1fef1f-47de-47c7-885f-f6f0a9a07d8c
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IDiaSymbol::get_sealed
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

클래스 또는 메서드는 봉인 되어 있는지 여부를 지정 하는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_sealed(   
   BOOL* pRetVal)  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 클래스 또는 메서드를 봉인 한 경우; 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 봉인 클래스는 기본 클래스로 사용할 수 없습니다.  봉인된 메서드 재정의 되 면 수 없습니다.  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
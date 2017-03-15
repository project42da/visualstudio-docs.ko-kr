---
title: "IDiaSymbol::get_virtualBaseDispIndex | Microsoft Docs"
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
  - "IDiaSymbol::get_virtualBaseDispIndex 메서드"
ms.assetid: 5561a3cb-2c82-41cf-9217-3ee2b1e1d1d1
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_virtualBaseDispIndex
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기본 가상 치환 테이블에서 인덱스를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_virtualBaseDispIndex (  
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 가상 기본 위치 변경 테이블에 있는 인덱스를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
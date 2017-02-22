---
title: "IDiaSymbol::get_language | Microsoft Docs"
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
  - "IDiaSymbol::get_language 메서드"
ms.assetid: c759ad3c-1c21-4234-869b-86aa3a608a38
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_language
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

언어는 소스를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_language (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 값을 반환의 [CV\_CFL\_LANG 열거형](../../debugger/debug-interface-access/cv-cfl-lang.md) 의 원본 언어를 지정 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [CV\_CFL\_LANG 열거형](../../debugger/debug-interface-access/cv-cfl-lang.md)
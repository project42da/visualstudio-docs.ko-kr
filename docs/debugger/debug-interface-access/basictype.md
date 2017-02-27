---
title: "BasicType | Microsoft Docs"
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
  - "BasicType 열거형"
ms.assetid: 19ae53ba-cd6e-47b6-9f94-27ae663ce955
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# BasicType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

심볼의 기본 형식을 지정합니다.  
  
## 구문  
  
```cpp#  
enum BasicType {   
   btNoType   = 0,  
   btVoid     = 1,  
   btChar     = 2,  
   btWChar    = 3,  
   btInt      = 6,  
   btUInt     = 7,  
   btFloat    = 8,  
   btBCD      = 9,  
   btBool     = 10,  
   btLong     = 13,  
   btULong    = 14,  
   btCurrency = 25,  
   btDate     = 26,  
   btVariant  = 27,  
   btComplex  = 28,  
   btBit      = 29,  
   btBSTR     = 30,  
   btHresult  = 31  
};  
```  
  
## Elements  
 btNoType  
 기본 형식이 지정 됩니다.  
  
 btVoid  
 기본 형식에 `void`.  
  
 btChar  
 기본 형식에 `char` \(C\/C\+\+ 형식\)입니다.  
  
 btWChar  
 와이드 \(유니코드\) 문자 기본 형식인 \(`WCHAR`\).  
  
 btInt  
 기본 형식 `signed int` \(C\/C\+\+ 형식\)입니다.  
  
 btUInt  
 기본 형식 `unsigned int` \(C\/C\+\+ 형식\)입니다.  
  
 btFloat  
 기본 형식은 부동 소수점 숫자입니다 \(`FLOAT`\).  
  
 btBCD  
 기본 형식인 이진 코딩 된 소수 \(`BCD`\).  
  
 btBool  
 기본 형식은 부울입니다 \(`BOOL`\).  
  
 btLong  
 기본 형식에 `long int` \(C\/C\+\+ 형식\)입니다.  
  
 btULong  
 기본 형식에 `unsigned long int` \(C\/C\+\+ 형식\)입니다.  
  
 btCurrency  
 기본 통화입니다.  
  
 btDate  
 날짜\/시간 기본 형식인 \(`DATE`\).  
  
 btVariant  
 기본 형식인 변수 형식 구조 \(`VARIANT`\).  
  
 btComplex  
 기본 형식은 복잡 한 숫자입니다.  
  
 btBit  
 기본 형식은 약간입니다.  
  
 btBSTR  
 기본 형식인 기본 또는 이진 문자열 \(`BSTR`\).  
  
 btHresult  
 기본 형식에 `HRESULT`.  
  
## 설명  
 이 열거형의 값으로 반환 되는 [IDiaSymbol::get\_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md) 방법입니다.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaSymbol::get\_baseType](../../debugger/debug-interface-access/idiasymbol-get-basetype.md)   
 [IDiaSymbol::get\_length](../../debugger/debug-interface-access/idiasymbol-get-length.md)
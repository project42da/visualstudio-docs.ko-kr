---
title: "IDiaEnumSymbols::Next | Microsoft Docs"
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
  - "IDiaEnumSymbols::Next 메서드"
ms.assetid: bfe5fe27-6a84-4392-910f-e325146d7552
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSymbols::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 수 만큼 열거 시퀀스에서 기호를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next (   
   ULONG        celt,  
   IDiaSymbol** rgelt,  
   ULONG*       pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 기호 수를에서 열거자를 검색할 수 있습니다.  
  
 rgelt  
 \[out\] 배열을 사용 하 여 입력 하는 것은 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 원하는 기호를 나타내는 개체입니다.  
  
 pceltFetched  
 \[out\] 기호에 반입 된 열거자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 있는 경우 더 이상 기호입니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
  
```cpp#  
IDiaEnumSymbols* pEnum  
CComPtr< IDiaSymbol> pSym;  
DWORD celt;  
pEnum->Next( 1, &pSym, &celt );  
```  
  
## 참고 항목  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession::findLinesByLinenum](../../debugger/debug-interface-access/idiasession-findlinesbylinenum.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
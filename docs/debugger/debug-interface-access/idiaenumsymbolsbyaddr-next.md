---
title: "IDiaEnumSymbolsByAddr::Next | Microsoft Docs"
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
  - "IDiaEnumSymbolsByAddr::Next 메서드"
ms.assetid: a1320587-7ce7-401f-9548-2f8bcece5cc3
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSymbolsByAddr::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

순서에서 다음 기호에서 주소를 검색합니다.  
  
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
  
## 설명  
 이 메서드는 열거자의 위치 반입 요소 수로 업데이트 합니다.  
  
## 참고 항목  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: "IDiaEnumSymbolsByAddr::symbolByRVA | Microsoft Docs"
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
  - "IDiaEnumSymbolsByAddr::symbolByRVA 메서드"
ms.assetid: f7828029-f2ee-4ccd-afac-785adc60a4c8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumSymbolsByAddr::symbolByRVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거자가 상대 가상 주소 \(RVA\)에서 조회를 수행 하 여 배치 합니다.  
  
## 구문  
  
```cpp#  
HRESULT symbolByRVA (   
   DWORD**      relativeVirtualAddress,  
   IDiaSymbol** ppsymbol  
);  
```  
  
#### 매개 변수  
 relativeVirtualAddress  
 \[in\] 이미지를 시작 하는 상대 주소입니다.  
  
 ppsymbol  
 \[out\] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 찾을 수를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 기호를 찾을 수 없습니다 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)   
 [IDiaEnumSymbolsByAddr::symbolByVA](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr-symbolbyva.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
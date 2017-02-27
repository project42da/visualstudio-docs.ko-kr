---
title: "IDiaSymbol::findInlineeLinesByRVA | Microsoft Docs"
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
ms.assetid: ac108db1-9dbf-4dc4-bf48-159ca8d3725c
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::findInlineeLinesByRVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거형에는 줄 번호 정보를 직접 또는 간접적으로,이 기호는 지정한 상대 가상 주소 \(RVA\) 내에서 인라인, 될 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findInlineeLinesByRVA (   
   DWORD                 rva,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `rva`  
 \[in\] 주소는 RVA로 지정합니다.  
  
 `length`  
 \[in\] 주소 범위에이 쿼리를 포함 하는 바이트 수를 지정 합니다.  
  
 `ppResult`  
 \[out\] 보유 하 고 있는 `IDiaEnumLineNumbers` 목록을 검색 하는 줄 번호를 포함 하는 개체입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession::findInlineeLines](../../debugger/debug-interface-access/idiasession-findinlineelines.md)
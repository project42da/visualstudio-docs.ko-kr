---
title: "IDiaSymbol::findInlineeLinesByAddr | Microsoft Docs"
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
ms.assetid: f1ab47ca-c851-48ea-9c12-47fb80b31102
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::findInlineeLinesByAddr
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거형에는 줄 번호 정보를 직접 또는 간접적으로,이 기호는 지정 된 주소 범위 내에서 인라인인 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findInlineeLinesByAddr (   
   DWORD                 isect,  
   DWORD                 offset,  
   DWORD                 length,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `isect`  
 \[in\] 주소의 섹션 구성 요소를 지정합니다.  
  
 `offset`  
 \[in\] 주소의 오프셋 구성 요소를 지정합니다.  
  
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
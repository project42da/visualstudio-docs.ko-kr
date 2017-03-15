---
title: "IDiaSession::getSymbolsByAddr | Microsoft Docs"
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
  - "IDiaSession::getSymbolsByAddr 메서드"
ms.assetid: eafcc757-b488-487d-a063-ad3703ff42e8
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSession::getSymbolsByAddr
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호는 주소 순서에 따라 검색 하는 열거자를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT getSymbolsByAddr(   
   IDiaEnumSymbolsByAddr** ppEnumbyAddr  
);  
```  
  
#### 매개 변수  
 `ppEnumbyAddr`  
 \[out\] 반환 된 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md) 개체입니다.  이 인터페이스를 사용 하 여 기호를 기호 저장소 메모리 위치에서 검색할 수 있습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)
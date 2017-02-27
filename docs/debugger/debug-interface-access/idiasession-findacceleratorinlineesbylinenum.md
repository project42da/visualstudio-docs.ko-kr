---
title: "IDiaSession::findAcceleratorInlineesByLinenum | Microsoft Docs"
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
ms.assetid: 386c87aa-f7b2-4d38-9dd6-fffba9ff01f0
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSession::findAcceleratorInlineesByLinenum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거형의 기호에 해당 하는 인라인 프레임을 지정 된 소스 위치를 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findAcceleratorInlineeLinesByName (   
   IDiaSymbol*           parent,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 colnum,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `parent`  
 \[in\] `IDiaSymbol` 를 검색 하는 데 필요한 가속기 스텁 함수에 해당 합니다.  
  
 `file`  
 \[in\] `IDiaSourceFile` 원본 위치입니다.  
  
 `linenum`  
 \[in\] 원본 위치의 줄 번호입니다.  
  
 `colnum`  
 \[in\] 원본 위치의 열 번호입니다.  
  
 `ppResult`  
 \[out\] 에 대 한 포인터는 `IDiaEnumLineNumbers` 결과로 초기화 된 인터페이스 포인터입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
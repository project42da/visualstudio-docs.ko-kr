---
title: "IDiaSession::findInlineeLinesByLinenum | Microsoft Docs"
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
ms.assetid: cf32ae7c-a0c8-4800-bc8f-d64fdd15fb06
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSession::findInlineeLinesByLinenum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거형에는 줄 번호 정보를 직접 또는 간접적으로 지정 된 소스 파일 및 줄 번호를에서 인라인인 모든 함수를 반복 하는 클라이언트 수를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findInlineeLinesByVA (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   DWORD                 linenum,  
   DWORD                 column,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `compiland`  
 \[in\] 줄 번호를 검색할 컴파일 대상을 나타내는 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 개체입니다.  이 매개 변수는 `NULL`일 수 없습니다.  
  
 `file`  
 \[in\] [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 검색할 원본 파일을 나타내는 개체입니다.  이 매개 변수는 `NULL`일 수 없습니다.  
  
 `linenum`  
 \[in\] 1부터 시작하는 줄 번호를 지정합니다.  
  
> [!NOTE]
>  모든 줄을 지정하려면 0을 사용할 수 없습니다\(사용 하는 [IDiaSession::findLines](../../debugger/debug-interface-access/idiasession-findlines.md) 메서드를 사용하여 모든 줄을 찾습니다\).  
  
 `column`  
 \[in\] 열 번호를 지정합니다.  0을 사용하여 모든 열을 지정합니다.  열은 줄의 바이트 오프셋입니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 검색 된 줄 번호를 포함 하는 개체입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)
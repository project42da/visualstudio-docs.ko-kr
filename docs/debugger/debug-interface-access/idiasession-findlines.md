---
title: "IDiaSession::findLines | Microsoft Docs"
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
  - "IDiaSession::findLines 메서드"
ms.assetid: d6e84916-fd55-457e-b057-57f97b51fe73
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSession::findLines
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 된 컴파일 대상 및 원본 파일 식별자에 줄 번호를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT findLines (   
   IDiaSymbol*           compiland,  
   IDiaSourceFile*       file,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `compiland`  
 \[in\][IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 컴파일 대상 개체입니다.  이 인터페이스를 사용 하 여 컨텍스트 줄 번호에 대 한 검색으로.  
  
 `file`  
 \[in\] [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md) 소스 파일 검색에 대 한 줄 번호를 나타내는 개체입니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md) 줄 번호 목록을 포함 하는 개체를 검색 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumLineNumbers](../../debugger/debug-interface-access/idiaenumlinenumbers.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSourceFile](../../debugger/debug-interface-access/idiasourcefile.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
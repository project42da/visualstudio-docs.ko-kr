---
title: "IDiaSession::findInlineesByName | Microsoft Docs"
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
ms.assetid: 9860336d-f703-4ecb-bfc4-3f5beb175a76
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSession::findInlineesByName
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 이름과 일치 하는 모든 인라인된 함수 줄 번호 정보를 통해 반복 하는 클라이언트가 열거형을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findInlineesByName (   
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumLineNumbers** ppResult  
);  
```  
  
#### 매개 변수  
 `name`  
 \[in\] 비교에 사용할 이름을 지정 합니다.  
  
 `option`  
 \[in\] 이름 검색에 적용된 비교 옵션을 지정합니다.  [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 값은 단독으로 또는 조합하여 사용할 수 있습니다.  
  
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
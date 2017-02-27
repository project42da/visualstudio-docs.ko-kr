---
title: "IDiaSession::symbolById | Microsoft Docs"
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
  - "IDiaSession::symbolById 메서드"
ms.assetid: 062e4b5a-9c4d-4703-88da-ec13102c2b66
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSession::symbolById
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호에서 고유 식별자를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT symbolById (   
   DWORD        id,  
   IDiaSymbol** ppSymbol  
);  
```  
  
#### 매개 변수  
 `id`  
 \[in\] 고유 식별자입니다.  
  
 `ppSymbol`  
 \[out\] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 나타내는 개체를 검색 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 지정 된 식별자를 내부적으로 DIA SDK에서 사용 되는 모든 기호를 고유 하 게 하는 고유한 값입니다.  
  
 이 메서드, 예를 들어, 다른 심볼의 유형을 나타내는 기호를 검색할 수 사용할 수 있습니다 \(예제 참조\).  
  
## 예제  
 검색 하는이 예제는 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 다른 심볼의 유형을 표시 합니다.  사용 하는 방법을 보여 주는이 예제는 `symbolById` 메서드는 세션에서.  호출 하는 것이 더 간단한 접근은 [IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md) 형식 기호를 직접 검색 하는 방법.  
  
```cpp#  
IDiaSymbol *GetSymbolType(IDiaSymbol *pSymbol, IDiaSession *pSession)  
{  
    IDiaSymbol *pTypeSymbol = NULL;  
    if (pSymbol != NULL && pSession != NULL)  
    {  
        DWORD symbolTypeId;  
        pSymbol->get_typeId(&symbolTypeId);  
        pSession->symbolById(symbolTypeId, &pTypeSymbol);  
    }  
    return(pTypeSymbol);  
}  
```  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get\_type](../../debugger/debug-interface-access/idiasymbol-get-type.md)
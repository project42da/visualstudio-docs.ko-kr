---
title: "IDiaSymbol::findChildrenEx | Microsoft Docs"
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
  - "IDiaSymbol::findChildrenEx"
ms.assetid: 6e045045-da8c-4338-9423-81a1ca20c405
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSymbol::findChildrenEx
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

심볼의 자식을 검색합니다.  프로그램에서 최적화 하 여 컴파일할 경우 반환 되는 지역 기호 라이브 범위 정보를 포함 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findChildrenEx (   
   enum SymTagEnum   symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### 매개 변수  
 `symtag`  
 \[in\] 정의 된 기호 태그 검색 해야 하는 자식 지정은 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md).  설정 `SymTagNull` 검색 해야 하는 모든 어린이.  
  
 `name`  
 \[in\] 검색할 자식 항목의 이름을 지정 합니다.  설정 `NULL` 검색 해야 하는 모든 어린이.  
  
 `compareFlags`  
 \[in\] 이름이 일치 하는에 적용 될 수 있는 비교 옵션을 지정 합니다.  값은 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 단독으로 또는 조합 하 여 사용할 수 있습니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록을 포함 하는 개체를 검색 합니다.  
  
## 반환 값  
 반환 `S_OK` 반환 하거나 발견 된 심볼의 하나 이상의 자식 경우 `S_FALSE` 하위 항목이 있는 경우; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 방법의 확장 된 버전입니다 [IDiaSymbol::findChildren](../../debugger/debug-interface-access/idiasymbol-findchildren.md).  
  
## 요구 사항  
 헤더: Dia2.h  
  
 라이브러리: diaguids.lib  
  
 DLL: msdia100.dll  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)
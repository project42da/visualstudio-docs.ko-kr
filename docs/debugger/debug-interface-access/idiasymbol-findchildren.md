---
title: "IDiaSymbol::findChildren | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IDiaSymbol::findChildren 메서드"
ms.assetid: 5fe7573a-e48b-428d-9c17-7421b7209246
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::findChildren
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

심볼의 자식을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT findChildren (   
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
 \[in\] 이름이 일치 하는에 적용할 비교 옵션을 지정 합니다.  값은 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 단독으로 또는 조합 하 여 사용할 수 있습니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록을 포함 하는 개체를 검색 합니다.  
  
## 반환 값  
 반환 `S_OK` 반환 하거나 발견 된 심볼의 하나 이상의 자식 경우 `S_FALSE` 하위 항목이 있는 경우; 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드 호출에 동일은 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md) 메서드를이 기호 첫 번째 매개 변수로 사용 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)
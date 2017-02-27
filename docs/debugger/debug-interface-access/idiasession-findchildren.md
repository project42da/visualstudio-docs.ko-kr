---
title: "IDiaSession::findChildren | Microsoft Docs"
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
  - "IDiaSession::findChildren 메서드"
ms.assetid: 5d19046f-f668-4aa9-8788-95cda9a98997
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaSession::findChildren
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이름과 기호 일치는 지정 된 부모 id의 모든 자식 항목을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findChildren (   
   IDiaSymbol*       parent,  
   SymTagEnum        symtag,  
   LPCOLESTR         name,  
   DWORD             compareFlags,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### 매개 변수  
 `parent`  
 \[in\] [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 의 부모를 나타내는 개체입니다.  함수, 모듈 또는 블록,이 부모 심볼 인 경우 어휘 자식을 반환 됩니다 `ppResult`.  다음 클래스 자식 부모 기호 형식인 경우 반환 됩니다.  이 매개 변수가 `NULL`, 다음 `symtag` 설정 되어야 합니다 `SymTagExe` 또는 `SymTagNull`, 전역 범위 \(.exe 파일\)을 반환 합니다.  
  
 `symtag`  
 \[in\] 검색할 하위 symbol 태그를 지정 합니다.  값에서 결정 되는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형입니다.  설정 `SymTagNull` 모든 자식을 검색할 수 있습니다.  
  
 `name`  
 \[in\] 검색할 자식 항목의 이름을 지정 합니다.  설정 `NULL` 검색 해야 하는 모든 어린이.  
  
 `compareFlags`  
 \[in\] 이름이 일치 하는에 적용할 비교 옵션을 지정 합니다.  값은 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md) 열거형 단독으로 또는 조합 하 여 사용할 수 있습니다.  
  
 `ppResult`  
 \[out\] 반환 된 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md) 자식 기호 목록이 포함 된 개체를 검색 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
 다음 예제에서는 함수에 로컬 변수를 찾는 방법을 보여 줍니다. `pFunc` 는 일치 하는 이름 `szVarName`.  
  
```cpp#  
IDiaEnumSymbols* pEnum;  
pSession->findChildren( pFunc, SymTagData, szVarName, nsCaseSensitive, &pEnum );  
```  
  
## 참고 항목  
 [개요](../../debugger/debug-interface-access/overview-debug-interface-access-sdk.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
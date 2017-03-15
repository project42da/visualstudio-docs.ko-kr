---
title: "IDiaEnumTables::Item | Microsoft Docs"
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
  - "IDiaEnumTables::Item 메서드"
ms.assetid: d65ab262-10c6-48ce-95a3-b5e4cb2c85af
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# IDiaEnumTables::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

테이블의 인덱스 또는 이름으로 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   VARIANT     index,  
   IDiaTable** table  
);  
```  
  
#### 매개 변수  
 `index`  
 \[in\] 인덱스 또는 이름을 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 검색할 수 있습니다.  정수 변수를 사용 하는 경우 범위가 0 이어야 합니다 `count`\-1, 어디 `count` 에서 반환 하는 것의 [IDiaEnumTables::get\_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md) 메서드.  
  
 `table`  
 \[out\] 반환 된 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 테이블을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 다음 문자열 변수를 지정 하지 않으면 문자열이 특정 테이블을 이름을 지정 합니다.  이름은 테이블 이름 중 하나에 정의 된 이어야 합니다 [상수\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md).  
  
## 예제  
  
```cpp#  
VARIANT var;  
var.vt = VT_BSTR;  
var.bstrVal = SysAllocString(DiaTable_Symbols );  
IDiaTable* pTable;  
pEnumTables->Item( var, &pTable );  
```  
  
## 참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)   
 [IDiaEnumTables::get\_Count](../../debugger/debug-interface-access/idiaenumtables-get-count.md)   
 [상수\(디버그 인터페이스 액세스 SDK\)](../../debugger/debug-interface-access/constants-debug-interface-access-sdk.md)
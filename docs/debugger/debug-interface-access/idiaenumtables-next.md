---
title: "IDiaEnumTables::Next | Microsoft Docs"
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
  - "IDiaEnumTables::Next 메서드"
ms.assetid: 8d7bd359-d33e-4317-9674-d89283efd7de
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaEnumTables::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

테이블 열거 시퀀스에서 지정 된 시간을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next (   
   ULONG       celt,  
   IDiaTable** rgelt,  
   ULONG*      pceltFetched  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 열거자를 검색할 테이블 개수입니다.  
  
 `rgelt`  
 \[out\] 배열을 사용 하 여 입력 하는 것은 [IDiaTable](../../debugger/debug-interface-access/idiatable.md) 원하는 테이블을 나타내는 개체입니다.  
  
 `pceltFetched`  
 \[out\] 테이블에 반입 된 열거자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 있는 경우 테이블을 더 합니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumTables](../../debugger/debug-interface-access/idiaenumtables.md)   
 [IDiaTable](../../debugger/debug-interface-access/idiatable.md)
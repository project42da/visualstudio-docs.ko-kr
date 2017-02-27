---
title: "IDiaPropertyStorage::ReadBOOL | Microsoft Docs"
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
  - "IDiaPropertyStorage::ReadBOOL"
ms.assetid: ad1822db-4572-48f7-9919-f8137f6701f2
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaPropertyStorage::ReadBOOL
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

읽고 `BOOL` 속성 집합 값입니다.  
  
## 구문  
  
```cpp#  
HRESULT ReadBOOL (   
   PROPID id,  
   BOOL*  pValue  
);  
```  
  
#### 매개 변수  
 `id`  
 \[in\] 읽을 수 있도록 하는 속성의 식별자 \(`PROPID` Wtypes.h로 정의 되는 `ULONG`\).  
  
 `pValue`  
 \[out\] 속성 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_INVALIDARG` 속성의 형식인 경우 `BOOL`.  
  
## 설명  
 일관 된 결과를 해석의 `BOOL` 0이 아닌 값은 값 `TRUE` 0입니다 및 `FALSE`.  
  
## 참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
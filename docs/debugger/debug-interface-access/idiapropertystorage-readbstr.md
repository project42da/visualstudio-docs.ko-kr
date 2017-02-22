---
title: "IDiaPropertyStorage::ReadBSTR | Microsoft Docs"
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
  - "IDiaPropertyStorage::ReadBSTR"
ms.assetid: 7214643b-3286-48ed-90aa-0fe95b4cae5b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaPropertyStorage::ReadBSTR
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

읽고 `BSTR` 속성 집합 값입니다.  
  
## 구문  
  
```cpp#  
HRESULT ReadBSTR (   
   PROPID id,  
   BSTR*  pValue  
);  
```  
  
#### 매개 변수  
 `id`  
 \[in\] 읽을 수 있도록 하는 속성의 식별자 \(`PROPID` Wtypes.h로 정의 되는 `ULONG`\).  
  
 `pValue`  
 \[out\] 속성 값을 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `E_INVALIDARG` 속성의 형식인 경우 `BSTR`.  
  
## 설명  
 A `BSTR` 0으로 끝나는 와이드 문자열 Windows에 의해 정의 됩니다.  
  
## 참고 항목  
 [IDiaPropertyStorage](../../debugger/debug-interface-access/idiapropertystorage.md)
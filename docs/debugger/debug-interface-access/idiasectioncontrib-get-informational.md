---
title: "IDiaSectionContrib::get_informational | Microsoft Docs"
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
  - "IDiaSectionContrib::get_informational 메서드"
ms.assetid: 5351e89f-7db1-4f8e-9e57-2dd1c74002e0
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IDiaSectionContrib::get_informational
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

섹션 설명 또는 유사한 정보가 포함 되어 있는지 여부를 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_informational(  
   BOOL* pRetVal  
};  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 구역 메모 또는 기타 정보; 포함 되어 있는 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 일반적으로.directive 섹션 정보를 포함합니다.  
  
## 참고 항목  
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
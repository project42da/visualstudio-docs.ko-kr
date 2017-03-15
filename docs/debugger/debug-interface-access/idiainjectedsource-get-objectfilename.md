---
title: "IDiaInjectedSource::get_objectFilename | Microsoft Docs"
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
  - "IDiaInjectedSource::get_objectFilename 메서드"
ms.assetid: 7c42847a-f0df-443a-a9fe-c495c1271ea8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaInjectedSource::get_objectFilename
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

소스를 컴파일한 개체 파일 이름을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_objectFilename (   
   BSTR* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 소스를 컴파일한 개체 파일 이름을 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaInjectedSource](../../debugger/debug-interface-access/idiainjectedsource.md)
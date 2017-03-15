---
title: "IDiaEnumDebugStreams::get_Count | Microsoft Docs"
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
  - "IDiaEnumDebugStreams::get_Count 메서드"
ms.assetid: 5c13fa9a-b35e-47b0-806f-1f53bfe1ba89
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumDebugStreams::get_Count
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버그 스트림을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_Count(   
   LONG* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 이 열거자에 사용할 수 있는 디버그 스트림을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumDebugStreams](../../debugger/debug-interface-access/idiaenumdebugstreams.md)   
 [IDiaEnumDebugStreams::Item](../../debugger/debug-interface-access/idiaenumdebugstreams-item.md)
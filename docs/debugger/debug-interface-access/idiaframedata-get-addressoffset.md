---
title: "IDiaFrameData::get_addressOffset | Microsoft Docs"
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
  - "IDiaFrameData::get_addressOffset 메서드"
ms.assetid: b68e2e68-6483-4936-bf97-1b0a13cb75e2
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaFrameData::get_addressOffset
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

오프셋된 부분의 코드 주소 프레임을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_addressOffset (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 오프셋된 부분의 코드 주소 프레임을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
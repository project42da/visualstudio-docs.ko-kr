---
title: "IDiaFrameData::get_addressSection | Microsoft Docs"
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
  - "IDiaFrameData::get_addressSection 메서드"
ms.assetid: e4eedede-4a1c-4da2-a812-b92df328fd8d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaFrameData::get_addressSection
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프레임에 대 한 코드 주소 구역 부분을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_addressSection (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 프레임에 대 한 코드 주소 구역 부분을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
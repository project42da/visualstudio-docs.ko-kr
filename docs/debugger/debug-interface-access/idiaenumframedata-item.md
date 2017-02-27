---
title: "IDiaEnumFrameData::Item | Microsoft Docs"
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
  - "IDiaEnumFrameData::Item 메서드"
ms.assetid: 2761a72d-1868-4f5b-a32e-c2a1d9358c91
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumFrameData::Item
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프레임 데이터 요소는 인덱스를 사용 하 여 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Item (   
   DWORD           index,  
   IDiaFrameData** section  
);  
```  
  
#### 매개 변수  
 인덱스\(index\)  
 \[in\] 색인은 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 검색할 개체입니다.  인덱스는 범위가 0입니다 `count`\-1, 어디 `count` 반환 하는 있는 [IDiaEnumFrameData::get\_Count](../../debugger/debug-interface-access/idiaenumframedata-get-count.md) 메서드.  
  
 섹션  
 \[out\] 반환 된 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 원하는 프레임 데이터 요소를 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
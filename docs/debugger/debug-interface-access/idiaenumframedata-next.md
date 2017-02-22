---
title: "IDiaEnumFrameData::Next | Microsoft Docs"
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
  - "IDiaEnumFrameData::Next 메서드"
ms.assetid: 546e2e23-efb2-425a-96a1-808c67c519fb
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumFrameData::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프레임 데이터 요소가 열거 시퀀스에서 지정 된 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next (   
   ULONG           celt,   
   IDiaFrameData** rgelt,  
   ULONG*          pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 열거자를 검색할 수 프레임 데이터 요소 수입니다.  
  
 rgelt  
 \[out\] 배열 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 개체는 요청 된 프레임 데이터 요소에 데이터를 입력할 수 있습니다.  
  
 pceltFetched  
 \[out\] 프레임 데이터 요소 수에서 반입 된 열거자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 레코드가 더 이상 없으면.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
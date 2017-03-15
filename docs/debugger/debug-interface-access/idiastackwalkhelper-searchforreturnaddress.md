---
title: "IDiaStackWalkHelper::searchForReturnAddress | Microsoft Docs"
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
  - "IDiaStackWalkHelper2::searchForReturnAddress 메서드"
ms.assetid: 904223b1-6e26-4980-b310-d0b222cdbbbd
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaStackWalkHelper::searchForReturnAddress
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 된 스택 프레임에 가까운 함수의 반환 주소를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT searchForReturnAddress(   
   IDiaFrameData*  frame,  
   ULONGLONG*      returnAddress  
);  
```  
  
#### 매개 변수  
 `frame`  
 \[in\] [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 는 현재 스택 프레임을 나타내는 개체입니다.  
  
 `returnAddress`  
 \[out\] 가까운 함수의 반환 주소를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
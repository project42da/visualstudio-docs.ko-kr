---
title: "IDiaStackWalkFrame::searchForReturnAddressStart | Microsoft Docs"
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
  - "IDiaStackWalkFrame::searchForReturnAddressStart 메서드"
ms.assetid: 47660b9b-6e4f-4dfa-88ab-63dce28f7412
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaStackWalkFrame::searchForReturnAddressStart
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

반송 주소 또는 지정한 주소 근처에 대해 지정 된 스택 프레임을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT searchForReturnAddressStart (   
   IDiaFrameData* frame,  
   ULONGLONG      startAddress,  
   ULONGLONG*     returnAddress  
);  
```  
  
#### 매개 변수  
 `frame`  
 \[in\] [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 는 현재 스택 프레임을 나타내는 개체입니다.  
  
 `startAddress`  
 \[in\] 가상 메모리 주소에서 검색을 시작 합니다.  
  
 `returnAddress`  
 \[out\] 반송 주소를 가까운 함수 반환 `startAddress`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
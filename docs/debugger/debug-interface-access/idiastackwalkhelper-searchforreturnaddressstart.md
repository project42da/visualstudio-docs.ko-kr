---
title: "IDiaStackWalkHelper::searchForReturnAddressStart | Microsoft Docs"
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
  - "IDiaStackWalkHelper::searchForReturnAddressStart 메서드"
ms.assetid: 0a33142e-5d31-44ea-874a-a2e94d95cbd2
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaStackWalkHelper::searchForReturnAddressStart
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

반송 주소 또는 지정 된 스택 주소 근처에 대해 지정 된 스택 프레임을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT searchForReturnAddressStart(   
   IDiaFrameData*  frame,  
   ULONGLONG       startAddress,  
   ULONGLONG*      returnAddress  
);  
```  
  
#### 매개 변수  
 `frame`  
 \[in\] [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 는 현재 스택 프레임을 나타내는 개체입니다.  
  
 `startAddress`  
 \[in\] 가상 메모리 주소에서 검색을 시작 합니다.  
  
 `ReturnAddress`  
 \[out\] 반송 주소를 가까운 함수 반환 `startAddress`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
---
title: "IDiaEnumFrameData::frameByVA | Microsoft Docs"
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
  - "IDiaEnumFrameData::frameByVA 메서드"
ms.assetid: 0b1e441b-710a-46d8-8060-bed39071c834
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumFrameData::frameByVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

가상 주소 \(VA\)에서 프레임을 반환합니다.  
  
## 구문  
  
```cpp#  
HRESULT frameByVA(   
   ULONGLONG       virtualAddress,  
   IDiaFrameData** frame  
);  
```  
  
#### 매개 변수  
 virtualAddress  
 \[in\] VA 관심의 프레임입니다.  
  
 프레임  
 \[out\] 반환 된 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md) 주소로 포함 된 프레임을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 프레임 데이터가 지정 된 주소와 일치 하는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)   
 [IDiaFrameData](../../debugger/debug-interface-access/idiaframedata.md)
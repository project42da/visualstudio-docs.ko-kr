---
title: "IDiaEnumFrameData::Skip | Microsoft Docs"
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
  - "IDiaEnumFrameData::Skip 메서드"
ms.assetid: 67140b4c-7125-4895-932d-42412326da29
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumFrameData::Skip
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프레임 데이터 요소가 열거 시퀀스에서 지정 된 수를 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 열거형 시퀀스를 건너뛸 프레임 데이터 요소 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 건너뜁니다 레코드가 더 이상 없으면.  
  
## 참고 항목  
 [IDiaEnumFrameData](../../debugger/debug-interface-access/idiaenumframedata.md)
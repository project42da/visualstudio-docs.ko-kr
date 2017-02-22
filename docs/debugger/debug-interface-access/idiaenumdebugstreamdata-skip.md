---
title: "IDiaEnumDebugStreamData::Skip | Microsoft Docs"
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
  - "IDiaEnumDebugStreamData::Skip 메서드"
ms.assetid: 106ae1d3-a379-4077-babf-2665e697b0c4
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumDebugStreamData::Skip
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레코드는 열거 시퀀스에서 지정 된 수를 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 열거 시퀀스에서 건너뛸 레코드 개수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 건너뜁니다 레코드가 더 이상 없으면.  
  
## 참고 항목  
 [IDiaEnumDebugStreamData](../../debugger/debug-interface-access/idiaenumdebugstreamdata.md)
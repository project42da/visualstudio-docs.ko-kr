---
title: "IDiaEnumSymbols::Skip | Microsoft Docs"
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
  - "IDiaEnumSymbols::Skip 메서드"
ms.assetid: e601fbc9-b10b-41c7-8180-959e57efabe8
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSymbols::Skip
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 수 만큼 열거 시퀀스에서 기호를 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip (   
   ULONG celt  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 열거 시퀀스를 건너뛰려면 기호 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 있는 경우 더 이상 기호를 생략 합니다.  
  
## 참고 항목  
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
---
title: "IDiaEnumSectionContribs::Skip | Microsoft Docs"
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
  - "IDiaEnumSectionContribs::Skip 메서드"
ms.assetid: 7471a178-5134-41b2-80a6-51ff96abe916
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaEnumSectionContribs::Skip
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 수 만큼 열거 시퀀스에서 절 기 고물 건너뜁니다.  
  
## 구문  
  
```cpp#  
HRESULT Skip(   
   ULONG celt  
);  
```  
  
#### 매개 변수  
 `celt`  
 \[in\] 절 기 고물 건너뛰려면 열거 시퀀스에서의 수입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 있는 경우 건너뛸 수 없음 자세한 절 기 고물.  
  
## 참고 항목  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)
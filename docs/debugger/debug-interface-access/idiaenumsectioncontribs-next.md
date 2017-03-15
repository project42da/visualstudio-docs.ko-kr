---
title: "IDiaEnumSectionContribs::Next | Microsoft Docs"
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
  - "IDiaEnumSectionContribs::Next 메서드"
ms.assetid: a6bb2adb-ee6d-4f3c-ab5b-e89361c8880e
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSectionContribs::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

절 기 고물 열거 시퀀스에서 지정 된 시간을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next(   
   ULONG                celt,   
   IDiaSectionContrib** rgelt,  
   ULONG*               pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 수 절 기 고물에서 열거자를 검색할 수입니다.  
  
 rgelt  
 \[out\] 배열에 데이터를 입력할 수 있습니다에서 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md) 원하는 섹션 기여도 나타내는 개체입니다.  
  
 pceltFetched  
 \[out\] 절 기 고물 반입 열거자를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 있는 경우 없음 자세한 절 기 고물.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSectionContribs](../../debugger/debug-interface-access/idiaenumsectioncontribs.md)   
 [IDiaSectionContrib](../../debugger/debug-interface-access/idiasectioncontrib.md)
---
title: "IDiaSymbol::get_slot | Microsoft Docs"
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
  - "IDiaSymbol::get_slot 메서드"
ms.assetid: 97e405b8-483f-4da0-91e7-ca4d88251ecd
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSymbol::get_slot
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

슬롯 번호의 위치를 검색합니다.  Use when the [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) is `LocIsSlot`.  
  
## 구문  
  
```cpp#  
HRESULT get_slot (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 슬롯 번호의 위치를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)
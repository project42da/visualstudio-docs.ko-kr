---
title: "IDiaSymbol::get_locationType | Microsoft Docs"
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
  - "IDiaSymbol::get_locationType 메서드"
ms.assetid: fbb09c43-ebb7-4b4f-be53-ccff86eb183a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_locationType
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

데이터 기호 위치 유형을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_locationType (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 값에서의 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 같은 데이터 기호 위치 형식을 지정 하는 열거형 `static` 또는 `local`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)
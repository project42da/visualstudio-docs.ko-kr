---
title: "IDiaSymbol::get_offset | Microsoft Docs"
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
  - "IDiaSymbol::get_offset 메서드"
ms.assetid: 8292bb08-4dc8-4663-beb4-258f5d5a448d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_offset
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 위치 오프셋을 검색합니다.  Use when the [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) is `LocIsRegRel` or `LocIsBitField`.  
  
## 구문  
  
```cpp#  
HRESULT get_offset (   
   LONG* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 기호 위치를 바이트의 오프셋을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 오프셋은 이전에 결정 일부 지점에서입니다.  예를 들어, 오프셋에 대 한는 `LocIsBitField` 일반적으로 포함 하는 클래스의 시작에서 위치 형식입니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 7.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)
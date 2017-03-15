---
title: "IDiaSymbol::get_length | Microsoft Docs"
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
  - "IDiaSymbol::get_length 메서드"
ms.assetid: cc62f028-d195-4fbf-93bc-10b08bef52d2
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaSymbol::get_length
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 기호로 표시 되는 개체에 의해 사용 되는 메모리의 바이트 또는 비트의 수를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_length (   
   ULONGLONG* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 이 기호로 표시 되는 개체에 의해 사용 된 메모리의 비트 또는 바이트 수를 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 경우는 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md) 의 상징 `LocIsBitField`,이 메서드에서 반환 된 길이; 비트에 있습니다. 그렇지 않으면, 다른 모든 위치 형식 \(바이트\)에서입니다.  
  
## 예제  
  
```cpp#  
IDiaSymbol* pSymbol;  
ULONGLONG   length;  
pSymbol->get_length( &length );  
```  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 7.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [LocationType 열거형](../../debugger/debug-interface-access/locationtype.md)
---
title: "IDiaSymbol::get_thunkOrdinal | Microsoft Docs"
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
  - "IDiaSymbol::get_thunkOrdinal 메서드"
ms.assetid: 4b28d78a-1974-4d8a-8bb7-781bf630f2f4
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSymbol::get_thunkOrdinal
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

썽크 함수 유형을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_thunkOrdinal (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 값을 반환의 [THUNK\_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md) 함수 썽크 형식을 지정 하는 열거형입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 이 속성이 유효 하지 경우에만 기호 이름으로 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값이 `SymTagThunk`.  
  
 "썽크" 세그먼트화 된 주소 공간으로이 라고도 하는 16 비트 주소 공간을 32 비트 메모리 주소 공간 \(플랫 주소 공간이 라고도 함\) 사이의 변환 하는 코드 부분입니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [THUNK\_ORDINAL 열거형](../../debugger/debug-interface-access/thunk-ordinal.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
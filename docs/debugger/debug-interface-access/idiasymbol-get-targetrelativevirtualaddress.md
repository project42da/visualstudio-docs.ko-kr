---
title: "IDiaSymbol::get_targetRelativeVirtualAddress | Microsoft Docs"
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
  - "IDiaSymbol::get_targetRelativeVirtualAddress 메서드"
ms.assetid: 49a159f3-6943-44d3-90a3-0dba51e8a7ec
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaSymbol::get_targetRelativeVirtualAddress
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

썽크 대상의 상대 가상 주소 \(RVA\)를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_targetRelativeVirtualAddress (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 썽크 대상의 RVA를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 이 속성이 유효 하지 경우에만 기호 이름으로 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값이 `SymTagThunk`.  
  
 "썽크" 세그먼트화 된 주소 공간으로이 라고도 하는 16 비트 주소 공간을 32 비트 메모리 주소 공간 \(플랫 주소 공간이 라고도 함\) 사이의 변환 하는 코드 부분입니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
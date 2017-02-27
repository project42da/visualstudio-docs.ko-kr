---
title: "IDiaSymbol::get_oemSymbolId | Microsoft Docs"
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
  - "IDiaSymbol::get_oemSymbolId 메서드"
ms.assetid: 187801f0-bd82-4c5b-9fae-8eeb1a4ac0ce
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_oemSymbolId
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

원래 장비 제조업체 \(OEM\) 기호 ID 값을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_oemSymbolId (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환은 OEM 내부적으로 할당 된 id입니다. 기호  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 식별자는 DIA SDK를 고유 이름으로 모든 기호를 표시 하 여 만든 고유한 값입니다.  
  
 기호를 사용에이 속성이 적용 됩니다. 한 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 을 입력 `SymTagCustomType`.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
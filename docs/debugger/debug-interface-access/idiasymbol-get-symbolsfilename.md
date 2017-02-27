---
title: "IDiaSymbol::get_symbolsFileName | Microsoft Docs"
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
  - "IDiaSymbol::get_symbolsFileName 메서드"
ms.assetid: c1aa39ee-d645-431e-bf5f-0640c0998934
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_symbolsFileName
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호를 로드 된 파일의 이름을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_symbolsFileName (   
   BSTR* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 기호를 로드 하는 파일 이름을 반환 합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 심볼에 대해서만이 속성이 유효는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 값이 `SymTagExe` 는 전역 범위입니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
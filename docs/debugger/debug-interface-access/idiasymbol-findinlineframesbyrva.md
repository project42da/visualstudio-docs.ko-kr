---
title: "IDiaSymbol::findInlineFramesByRVA | Microsoft Docs"
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
ms.assetid: e7a6d9cb-2726-4ac7-9f38-415ad215bf9c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::findInlineFramesByRVA
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정한 상대 가상 주소 \(RVA\)에서 인라인 프레임을 통해 반복 하는 클라이언트가 열거형을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findInlineFramesByRVA (   
   DWORD             rva,  
   IDiaEnumSymbols** ppResult  
);  
```  
  
#### 매개 변수  
 `rva`  
 \[in\] 주소는 RVA로 지정합니다.  
  
 `ppResult`  
 \[out\] 보유 하 고 있는 `IDiaEnumSymbols` 검색 되는 프레임의 목록을 포함 하는 개체.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
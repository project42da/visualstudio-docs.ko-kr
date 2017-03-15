---
title: "IDiaSession::findSymbolByVAEx | Microsoft Docs"
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
  - "IDiaSession::findSymbolByVAEx 메서드"
ms.assetid: 11c685f6-cda2-4474-a432-214ecaae4ffa
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaSession::findSymbolByVAEx
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

있거나 지정한 가상 주소 \(VA\) 및 오프셋 하려면 가장 가까운 기호를 지정 된 형식으로 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findSymbolByVAEx (   
   ULONGLONG    va,  
   SymTagEnum   symtag,  
   IDiaSymbol** ppSymbol,  
   LONG*        displacement  
);  
```  
  
#### 매개 변수  
 `va`  
 \[in\] VA.를 지정합니다.  
  
 `symtag`  
 \[in\] 수 있는 심볼 유형입니다.  값에서 결정 되는 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md) 열거형입니다.  
  
 `ppSymbol`  
 \[out\] 반환 된 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 기호를 나타내는 개체를 검색 합니다.  
  
 `displacement`  
 \[out\] 주어진 가상 주소에서 오프셋을 지정 하는 값을 반환 합니다. `va`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 예제  
  
```cpp#  
IDiaSymbol* pFunc;  
LONG disp = 0;  
pSession->findSymbolByVAEx( va, SymTagFunction, &pFunc, &disp );  
```  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSession::findChildren](../../debugger/debug-interface-access/idiasession-findchildren.md)   
 [IDiaSession::findSymbolByVA](../../debugger/debug-interface-access/idiasession-findsymbolbyva.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [SymTagEnum 열거형](../../debugger/debug-interface-access/symtagenum.md)
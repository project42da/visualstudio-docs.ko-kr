---
title: "IDiaSession::symsAreEquiv | Microsoft Docs"
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
  - "IDiaSession::symsAreEquiv 메서드"
ms.assetid: 9941d520-e203-46c0-83c3-b3a967f4fc59
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSession::symsAreEquiv
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

확인 두 기호 동일한 지 확인 합니다.  
  
## 구문  
  
```cpp#  
HRESULT symsAreEquiv (   
   IDiaSymbol* symbolA,  
   IDiaSymbol* symbolB  
);  
```  
  
#### 매개 변수  
 `symbolA`  
 \[in\] 첫 번째 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 비교에 사용 되는 개체입니다.  
  
 `symbolB`  
 \[in\] 두 번째 `IDiaSymbol` 비교에 사용 되는 개체입니다.  
  
## 반환 값  
 기호가 같으면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE`, 기호는 서로 다릅니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
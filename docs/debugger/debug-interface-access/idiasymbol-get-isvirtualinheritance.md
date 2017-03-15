---
title: "IDiaSymbol::get_isVirtualInheritance | Microsoft Docs"
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
ms.assetid: 72906b92-dd4a-42e3-9b24-b77628fa48c1
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_isVirtualInheritance
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 여부는 `this` 포인터가 가리키는 데이터 멤버 가상 상속을 사용 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_isVirtualInheritance(   
   BOOL* pRetVal);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 에 대 한 포인터는 `BOOL` 지정 여부는 `this` 포인터가 가리키는 데이터 멤버 가상 상속을 사용 합니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
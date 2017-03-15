---
title: "IDiaEnumSymbolsByAddr::Clone | Microsoft Docs"
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
  - "IDiaEnumSymbolsByAddr::Clone 메서드"
ms.assetid: f4582c69-bc3f-4a26-bcca-b641102b85fe
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaEnumSymbolsByAddr::Clone
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

개체의 복사본을 만듭니다.  
  
## 구문  
  
```cpp#  
HRESULT Clone (   
   IDiaEnumSymbolsByAddr** ppenum  
);  
```  
  
#### 매개 변수  
 ppenum  
 \[out\] 반환 된 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md) 열거자의 복제본을 포함 하는 개체입니다.  기호가 중복 되지는 열거자입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumSymbolsByAddr](../../debugger/debug-interface-access/idiaenumsymbolsbyaddr.md)
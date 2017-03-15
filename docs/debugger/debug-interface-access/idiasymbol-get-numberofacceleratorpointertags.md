---
title: "IDiaSymbol::get_numberOfAcceleratorPointerTags | Microsoft Docs"
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
ms.assetid: 1886e3ec-b227-4187-8d93-c5144b4b77ae
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_numberOfAcceleratorPointerTags
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

가속기 포인터 태그 C\+\+ AMP 스텁 함수를 반환합니다.  
  
## 구문  
  
```cpp  
HRESULT get_numberOfAcceleratorPointerTags(   
   DWORD* count);  
```  
  
#### 매개 변수  
 `count`  
 \[out\] 에 대 한 포인터는 `DWORD` 가속기 수가 포인터 태그 C\+\+ AMP 스텁 함수를 포함 합니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 설명  
 이 메서드가 호출 되는 `IDiaSymbol` 인터페이스는 C\+\+ AMP 가속기 스텁 함수에 해당 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
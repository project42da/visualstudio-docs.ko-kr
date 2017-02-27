---
title: "IDiaSymbol::get_isAcceleratorPointerTagLiveRange | Microsoft Docs"
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
ms.assetid: d195aec4-6d3c-42e0-88a5-3d463539f0b8
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_isAcceleratorPointerTagLiveRange
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호에 해당 하는지 여부를 나타내는 플래그를 검색은  *정의 범위 기호* 포인터 변수는 C\+\+ AMP 가속기에 대 한 컴파일된 코드에서 태그 구성 요소에 대 한.  범위 정의 기호 주소 범위 변수의 위치입니다.  
  
## 구문  
  
```cpp  
HRESULT get_isAcceleratorPointerTagLiveRange(   
   BOOL* pFlag);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 에 대 한 포인터는 `BOOL` 기호 정의 범위 기호에 대응 하는지 나타냅니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
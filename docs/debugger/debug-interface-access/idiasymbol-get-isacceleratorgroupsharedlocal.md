---
title: "IDiaSymbol::get_isAcceleratorGroupSharedLocal | Microsoft Docs"
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
ms.assetid: 17a20542-5b45-478f-bb80-0d56031aadb5
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_isAcceleratorGroupSharedLocal
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호 그룹 공유 로컬 변수는 C\+\+ AMP 가속기에 대 한 컴파일된 코드에 해당 하는지 여부를 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_isAcceleratorGroupSharedLocal(   
   BOOL* pFlag);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 에 대 한 포인터는 `BOOL` 나타내는 기호 그룹 공유 로컬 변수는 C\+\+ AMP 가속기에 대 한 컴파일된 코드에 해당 하는지 여부.  경우 `TRUE`, `get_baseDataSlot` 및 `get_baseDataOffset` 메서드를 사용 하는 변수에 대 한 저장소 위치 정보를.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaSymbol::get\_baseDataSlot](../../debugger/debug-interface-access/idiasymbol-get-basedataslot.md)   
 [IDiaSymbol::get\_baseDataOffset](../../debugger/debug-interface-access/idiasymbol-get-basedataoffset.md)
---
title: "IDiaSymbol::get_isHLSLData | Microsoft Docs"
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
ms.assetid: 4662058b-c505-4ccf-ae03-739a62c814ca
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::get_isHLSLData
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 기호 높은 수준 셰이더 언어 \(HLSL\) 데이터를 나타내는지 여부를 지정 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_isHLSLData(   
   BOOL* pRetVal);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 에 대 한 포인터는 `BOOL` 이 기호 HLSL 데이터를 나타내는지 여부를 지정 합니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
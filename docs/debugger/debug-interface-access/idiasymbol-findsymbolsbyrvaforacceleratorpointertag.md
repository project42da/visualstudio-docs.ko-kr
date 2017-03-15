---
title: "IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag | Microsoft Docs"
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
ms.assetid: 024ccd78-5867-4ca7-bc26-548758e9ac53
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSymbol::findSymbolsByRVAForAcceleratorPointerTag
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

해당 태그 값이 주어진 경우이 메서드 스텁 함수에 지정한 상대 가상 주소에 포함 된 기호의 열거형을 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   DWORD             tagValue,  
   DWORD             rva,  
   IDiaEnumSymbols** ppResult);  
```  
  
#### 매개 변수  
 `tagValue`  
 \[in\] 포인터가 기호 pointee 레코드를 찾을 수 있는 태그 값입니다.  
  
 `rva`  
 \[in\] 지정 된 태그 값을 pointee 변수에 해당 기호를 필터링 하는 데 사용 되는 rva입니다.  
  
 `ppResult`  
 \[out\] 에 대 한 포인터는 `IDiaEnumSymbols` 의 결과로 초기화 인터페이스 포인터입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 설명  
 에서만이 메서드를 호출 하는 `IDiaSymbol` 인터페이스는 가속기 스텁 함수에 해당 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)
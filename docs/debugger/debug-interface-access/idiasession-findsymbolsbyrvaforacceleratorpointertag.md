---
title: "IDiaSession::findSymbolsByRVAForAcceleratorPointerTag | Microsoft Docs"
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
ms.assetid: a073cc45-0c7b-417e-b5fc-a3b08beccdbc
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSession::findSymbolsByRVAForAcceleratorPointerTag
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

해당 태그 값이 주어진 경우이 열거형에 포함 된 기호를 지정한 상대 가상 주소에 지정 된 부모 가속기 스텁 함수에서 반환 됩니다.  
  
## 구문  
  
```cpp#  
HRESULT findSymbolsByRVAForAcceleratorPointerTag (   
   IDiaSymbol*           parent,  
   DWORD                 tagValue,  
   DWORD                 rva,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### 매개 변수  
 `parent`  
 \[in\] `IDiaSymbol` 검색할 가속기 스텁 함수에 해당 합니다.  
  
 `tagValue`  
 \[in\] 포인터가 태그 값입니다.  
  
 `rva`  
 \[in\] 상대 가상 주소입니다.  
  
 `ppResult`  
 \[out\] 에 대 한 포인터는 `IDiaEnumSymbols` 결과로 초기화 된 인터페이스 포인터입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 에서만이 메서드를 호출 하는 `IDiaSymbol` 인터페이스는 가속기 스텁 함수에 해당 합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: "IDiaSession::findAcceleratorInlineesByName | Microsoft Docs"
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
ms.assetid: e203e5c2-6563-43fa-be56-3063955043ab
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IDiaSession::findAcceleratorInlineesByName
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

기호를 지정한 인라인 함수 이름에 해당 하는 인라인 프레임의 열거형을 반환 합니다.  
  
## 구문  
  
```cpp#  
HRESULT findAcceleratorInlineeLinesByName (   
   LPCOLESTR             name,  
   DWORD                 option,  
   IDiaEnumSymbols**     ppResult  
);  
```  
  
#### 매개 변수  
 `name`  
 \[in\] 검색할 인라인이 함수 이름입니다.  
  
 `option`  
 \[in\] 인라인에 대 한 검색은 프레임 때 사용할 이름 검색 옵션에 해당 `name`.  자세한 내용은 [NameSearchOptions 열거형](../../debugger/debug-interface-access/namesearchoptions.md)를 참조하십시오.  
  
 `ppResult`  
 \[out\] 에 대 한 포인터는 `IDiaEnumSymbols` 결과로 초기화 된 인터페이스 포인터입니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 오류 코드를 반환합니다.  
  
## 설명  
 이 함수를 inlinees 가속기 스텁 함수 내 에서만 검색합니다.  네이티브 C\+\+ 프로시저 레코드를 무시합니다.  
  
## 참고 항목  
 [IDiaSession](../../debugger/debug-interface-access/idiasession.md)   
 [IDiaEnumSymbols](../../debugger/debug-interface-access/idiaenumsymbols.md)   
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
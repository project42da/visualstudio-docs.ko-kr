---
title: "IDiaSymbol::get_acceleratorPointerTags | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 30e13cee-e511-49ec-affd-99b0097071b2
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_acceleratorPointerTags
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

C \+ \+ AMP 가속기 스텁 함수에 해당 하는 모든 가속기 포인터 태그 값을 반환 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_acceleratorPointerTags(   
   DWORD          cnt,  
   DWORD*         pcnt,  
   DWORD*         pPointerTags);  
```  
  
#### 매개 변수  
 `cnt`  
 \[in\] 출력 배열의 크기를 `pPointerTags`.  
  
 `pcnt`  
 \[out\] 가속기 가속기 C\+\+ AMP 스텁 함수 포인터 태그 개수입니다.  
  
 `pPointerTags`  
 \[out\] A `DWORD` 배열 포인터 C\+\+ AMP 가속기 스텁 함수 가속기 포인터 태그 값으로 채워집니다.  
  
## 반환 값  
 성공하면 `S_OK`를 반환하고, 그렇지 않으면 `S_FALSE` 또는 오류 코드를 반환합니다.  
  
## 설명  
 이 메서드가 호출 되는 `IDiaSymbol` 인터페이스는 C\+\+ AMP 가속기 스텁 함수에 해당 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
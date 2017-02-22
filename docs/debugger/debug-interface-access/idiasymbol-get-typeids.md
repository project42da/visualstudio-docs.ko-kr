---
title: "IDiaSymbol::get_typeIds | Microsoft Docs"
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
helpviewer_keywords: 
  - "IDiaSymbol::get_typeIds 메서드"
ms.assetid: 5166e647-fde5-4efe-92bf-77f8ae3fbc9b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_typeIds
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 기호 별 유형 식별자 값의 배열을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_typeIds (   
   DWORD  cTypeIds,  
   DWORD* pcTypeIds,  
   DWORD  typeIds[]  
);  
```  
  
#### 매개 변수  
 `cTypeIds`  
 \[in\] 데이터를 저장 하는 버퍼의 크기입니다.  
  
 `pcTypeIds`  
 \[out\] 수를 반환 합니다. `typeIds` 기록, 또는 if `typeIds` 입니다 `NULL`, 다음 총 사용 가능한 유형 식별자.  
  
 `typeIds[]`  
 \[out\] 형식 식별자를 사용 하 여 데이터를 입력할 수 있습니다 배열입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
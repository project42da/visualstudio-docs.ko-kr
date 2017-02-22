---
title: "IDiaSymbol::get_types | Microsoft Docs"
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
  - "IDiaSymbol::get_types 메서드"
ms.assetid: 5f056e0c-e15b-4e00-8f78-aadc8574f7ea
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_types
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 기호 별 형식의 배열을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_types (   
   DWORD       cTypes,  
   DWORD*      pcTypes,  
   IDiaSymbol* types[]  
);  
```  
  
#### 매개 변수  
 `cTypes`  
 \[in\] 데이터를 저장 하는 버퍼의 크기입니다.  
  
 `pcTypes`  
 \[out\] 작성 된 유형의 수를 반환 또는 if는 `types` 매개 변수입니다 `NULL`, 총 수 다음 형식 사용할 수 있습니다.  
  
 `types[]`  
 \[out\] 배열을 사용 하 여 입력 하는 것은 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md) 이 기호 모든 형식을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
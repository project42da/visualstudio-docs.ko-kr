---
title: "IDiaSymbol::get_platform | Microsoft Docs"
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
helpviewer_keywords: 
  - "IDiaSymbol::get_platform 메서드"
ms.assetid: dff1c1eb-bcb2-4275-bb07-f2fdc076d6fb
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaSymbol::get_platform
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

컴파일 대상에 대해 컴파일할 플랫폼 형식을 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_platform (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 값의 [CV\_CPU\_TYPE\_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 플랫폼을 지정 하는 열거형을 입력을 컴파일 컴파일 되었습니다에 대 한.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [CV\_CPU\_TYPE\_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md)
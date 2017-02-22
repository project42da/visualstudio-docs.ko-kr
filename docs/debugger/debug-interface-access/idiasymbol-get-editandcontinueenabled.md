---
title: "IDiaSymbol::get_editAndContinueEnabled | Microsoft Docs"
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
  - "IDiaSymbol::get_editAndContinueEnabled 메서드"
ms.assetid: cd703c64-9ff8-4654-8493-8cde9309cb22
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaSymbol::get_editAndContinueEnabled
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

검색 모듈을 컴파일한 여부를 나타내는 플래그를 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](/visual-cpp/build/reference/z7-zi-zi-debug-information-format) 컴파일러 스위치.  
  
## 구문  
  
```cpp#  
HRESULT get_editAndContinueEnabled (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 에서 컴파일을 합니다; 편집 하며 계속 하기 사용 되도록 설정 된 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 7.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [\/Z7, \/Zi, \/ZI\(디버깅 정보 형식\)](/visual-cpp/build/reference/z7-zi-zi-debug-information-format)
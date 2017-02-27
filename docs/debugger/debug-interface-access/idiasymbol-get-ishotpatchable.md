---
title: "IDiaSymbol::get_isHotpatchable | Microsoft Docs"
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
  - "IDiaSymbol::get_isHotpatchable 메서드"
ms.assetid: b7b6f490-1cf2-4a68-9237-b152dac84d3c
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_isHotpatchable
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

검색 모듈을 컴파일한 여부를 나타내는 플래그를 [\/hotpatch\(핫 패치 가능 이미지 만들기\)](/visual-cpp/build/reference/hotpatch-create-hotpatchable-image) 컴파일러 스위치.  
  
## 구문  
  
```cpp#  
HRESULT get_isHotpatchable(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 핫\-patchable; 모듈인 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 설명  
 이 속성에서 사용할 수 있는 `SymTagCompilandDetails` 형식 기호 \(참조 하십시오 [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)\).  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)   
 [CompilandDetails](../../debugger/debug-interface-access/compilanddetails.md)
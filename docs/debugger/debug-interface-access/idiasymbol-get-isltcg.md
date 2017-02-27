---
title: "IDiaSymbol::get_isLTCG | Microsoft Docs"
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
  - "IDiaSymbol::get_isLTCG 메서드"
ms.assetid: 5f7f05b8-6b71-4958-9e1e-e4924ef9c59b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_isLTCG
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 하는 플래그를 검색 하는지 여부는 [컴파일 대상](../../debugger/debug-interface-access/compiland.md) 링커 스위치와 연결 된 [\/LTCG\(링크 타임 코드 생성\)](/visual-cpp/build/reference/ltcg-link-time-code-generation), 전체 프로그램 최적화 기능을 도와줍니다.  이 스위치는 관리 되는 코드에만 적용 됩니다.  
  
## 구문  
  
```cpp  
HRESULT get_iSLTCG(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 pFlag  
 \[out\] 반환 `TRUE` 경우는 `compiland` \/LTCG 링커 스위치를 사용 합니다; 연결 된 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
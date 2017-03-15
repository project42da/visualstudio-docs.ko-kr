---
title: "IDiaSymbol::get_hasSecurityChecks | Microsoft Docs"
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
  - "IDiaSymbol::get_hasSecurityChecks 메서드"
ms.assetid: 4bb51f62-8645-41a4-bc44-1451010623fd
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IDiaSymbol::get_hasSecurityChecks
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

컴파일 또는 함수의 버퍼 오버런 보안 검사로 컴파일 되었는지 여부를 지정 하는 플래그를 검색 \(예를 들어 있는 [\/GS\(버퍼 보안 검사\)](/visual-cpp/build/reference/gs-buffer-security-check) 컴파일러 스위치\)입니다.  
  
## 구문  
  
```cpp#  
HRESULT get_hasSecurityChecks(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 경우 함수는 보안 검사. 그렇지 않으면 반환 `FALSE`.  
  
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
 [\/GS\(버퍼 보안 검사\)](/visual-cpp/build/reference/gs-buffer-security-check)
---
title: "IDiaSymbol::get_isDataAligned | Microsoft Docs"
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
  - "IDiaSymbol::get_isDataAligned 메서드"
ms.assetid: ddd11a41-6c00-4829-acf4-aa1ace8c21a7
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IDiaSymbol::get_isDataAligned
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자 정의 형식 \(UDT\) 일부 특정 메모리 경계에 정렬 되어 있는지 여부를 지정 하는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp  
HRESULT get_isDataAligned(  
   BOOL *pFlag  
);  
```  
  
#### 매개 변수  
 `pFlag`  
 \[out\] 반환 `TRUE` 일부 메모리 경계 하 고 UDT 맞춰진 경우 그렇지 않으면 반환 `FALSE`.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성에 사용할 수 있음을 의미 합니다.  
  
## 설명  
 일반적으로 기본이 아닌 데이터 정렬을 사용 하 여 실행 파일을 컴파일할 때이 속성을 설정 합니다.  Microsoft C\+\+ 컴파일러 명령줄 옵션을 사용 하면 데이터 맞춤을 변경할 수 있습니다 예를 들어, \/Zp*\#*, 어디  *\#* 바이트 값입니다.  
  
## 요구 사항  
  
|요구 사항|설명|  
|-----------|--------|  
|머리글:|dia2.h|  
|버전:|DIA SDK v 8.0|  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
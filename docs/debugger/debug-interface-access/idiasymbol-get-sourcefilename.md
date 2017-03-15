---
title: "IDiaSymbol::get_sourceFileName | Microsoft Docs"
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
  - "IDiaSymbol::get_sourceFileName 메서드"
ms.assetid: 0f5dce88-829e-4df3-8acd-8d71076ad167
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaSymbol::get_sourceFileName
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

컴파일 대상 소스 파일의 파일 이름을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_sourceFileName (   
   BSTR* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 컴파일 대상 소스 파일의 파일 이름을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 반환 `S_FALSE` 또는 오류 코드입니다.  
  
> [!NOTE]
>  반환 값이 `S_FALSE` 속성의 기호를 사용할 수 없음을 의미 합니다.  
  
## 참고 항목  
 [IDiaSymbol](../../debugger/debug-interface-access/idiasymbol.md)
---
title: "IDiaLineNumber::get_columnNumber | Microsoft Docs"
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
  - "IDiaLineNumber::get_columnNumber 메서드"
ms.assetid: e317f29a-6525-46a7-8421-33985392f8fd
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaLineNumber::get_columnNumber
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

식 또는 문 시작 되는 위치는 열 번호를 검색 합니다.  
  
## 구문  
  
```  
[C++]  
HRESULT get_columnNumber (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 식 또는 문 시작 되는 위치 열 번호를 반환 합니다.  값이 0 이면 다음 열 정보가 없는 것입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에서 반환 되는 열 값에 선 문 줄의 첫 번째 문자를 한 바이트 오프셋입니다.  
  
## 참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
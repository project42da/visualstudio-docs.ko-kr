---
title: "IDiaLineNumber::get_statement | Microsoft Docs"
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
  - "IDiaLineNumber::get_statement 메서드"
ms.assetid: 22b8ee29-79ef-427f-bd05-00d255ab836b
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# IDiaLineNumber::get_statement
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 줄 정보가 식 프로그램 소스에서 실행 하는 것이 아니라 명령문의 시작 부분에 설명 합니다 나타내는 플래그를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_statement (   
   BOOL* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 반환 `TRUE` 프로그램 소스에서 문 시작이 줄 정보를 설명 하는 경우.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 문을 여러 줄으로 나타낼 수 있습니다.  이 메서드는 연결 된 줄 번호가 여러 줄 문이의 시작을 표시 하는 경우를 나타냅니다.  
  
## 참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
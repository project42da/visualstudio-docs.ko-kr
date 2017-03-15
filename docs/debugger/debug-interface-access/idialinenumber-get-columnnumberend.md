---
title: "IDiaLineNumber::get_columnNumberEnd | Microsoft Docs"
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
  - "IDiaLineNumber::get_columnNumberEnd 메서드"
ms.assetid: 02fa56c1-87b6-405a-adee-3bb6bc62de2d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaLineNumber::get_columnNumberEnd
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

식 또는 문 끝나는 1 소스 열 번호를 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_columnNumberEnd (   
   DWORD* pRetVal  
);  
```  
  
#### 매개 변수  
 `pRetVal`  
 \[out\] 식 또는 문 끝나는 열 번호를 반환 합니다.  값이 0 이면 다음 열 끝 정보가 없습니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 이 속성이 지원 되지 않는 경우.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드에서 반환 되는 열 값 문의 줄에서 마지막 문자 뒤에 줄 위치 오프셋을 바이트입니다.  
  
## 참고 항목  
 [IDiaLineNumber](../../debugger/debug-interface-access/idialinenumber.md)
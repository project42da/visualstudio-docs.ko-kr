---
title: "IDiaEnumStackFrames::Next | Microsoft Docs"
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
  - "IDiaEnumStackFrames::Next 메서드"
ms.assetid: 09378a21-d5e3-4213-b7e2-10f04d85295f
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaEnumStackFrames::Next
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

열거형 시퀀스에서 지정된 된 스택 프레임 요소 수를 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT Next(   
   ULONG             celt,  
   IDiaStackFrame**  rgelt,  
   ULONG*            pceltFetched  
);  
```  
  
#### 매개 변수  
 celt  
 \[in\] 수 stackframe 검색할 표시기 요소입니다.  
  
 rgelt  
 \[out\] 요청을 채울 수 있도록 되어 있는 배열 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md) 개체입니다.  
  
 pceltFetched  
 \[out\] 스택 프레임 요소 반입 된 열거자를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`.  반환 `S_FALSE` 있는 경우 더 이상 스택 프레임이 없습니다.  그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)
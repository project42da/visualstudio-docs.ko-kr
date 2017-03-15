---
title: "IDiaStackFrame::get_registerValue | Microsoft Docs"
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
  - "IDiaStackFrame::get_registerValue 메서드"
ms.assetid: cbe3d8ac-319a-40ac-bc3e-4eb81b2d7807
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaStackFrame::get_registerValue
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정 된 레지스터의 값을 스택 프레임에서 저장 된 검색 합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_registerValue(  
   ULONG      registerIndex,  
   ULONGLONG *pRetVal  
);  
```  
  
#### 매개 변수  
 `registerIndex`  
 \[in\] 중 하나를 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 열거형 값입니다.  
  
 `pRetVal`  
 \[out\] 레지스터에 저장 된 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환합니다.  
  
## 참고 항목  
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)
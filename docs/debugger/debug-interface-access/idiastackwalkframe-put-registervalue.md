---
title: "IDiaStackWalkFrame::put_registerValue | Microsoft Docs"
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
  - "IDiaStackWalkFrame::put_registerValue 메서드"
ms.assetid: 2d8b79b6-7240-43fe-b24e-e4ff3e2c15b0
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaStackWalkFrame::put_registerValue
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레지스터의 값을 설정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT put_registerValue (   
   DWORD     index,  
   ULONGLONG NewVal  
);  
```  
  
#### 매개 변수  
 `index`  
 \[in\] 값은 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 쓰기 레지스터를 지정 하는 열거형입니다.  
  
 `NewVal`  
 \[in\] 새로운 레지스터 값입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDiaStackWalkFrame](../../debugger/debug-interface-access/idiastackwalkframe.md)   
 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)
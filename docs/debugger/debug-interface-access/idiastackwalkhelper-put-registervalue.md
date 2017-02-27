---
title: "IDiaStackWalkHelper::put_registerValue | Microsoft Docs"
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
  - "IDiaStackWalkHelper2::put_registerValue 메서드"
ms.assetid: 8f02ce54-ef59-455f-8aa6-dc26761c7aff
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDiaStackWalkHelper::put_registerValue
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
  
## 설명  
 값의 크기에도 불구 하 고 구현만 어떤 레지스터 일반적으로 보유를 저장 해야 합니다.  예를 들어, 8 비트 레지스터만의 최저 8\-비트를 지정 된 값을 포함할 수 있습니다.  
  
## 참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)
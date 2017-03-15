---
title: "IDiaStackWalkHelper::get_registerValue | Microsoft Docs"
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
  - "IDiaStackWalkHelper2::get_registerValue 메서드"
ms.assetid: 46ac5eee-73a3-44a1-8635-6c58ba193cb6
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IDiaStackWalkHelper::get_registerValue
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

레지스터의 값을 검색합니다.  
  
## 구문  
  
```cpp#  
HRESULT get_registerValue (   
   DWORD      index,  
   ULONGLONG* pRetVal  
);  
```  
  
#### 매개 변수  
 `index`  
 \[in\] 값은 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md) 값을 가져올 등록할 지정 하는 열거형입니다.  
  
 `pRetVal`  
 \[out\] 레지스터의 현재 값을 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 크기에도 불구 하 고 있는 `pRetVal` 매개 변수를 구현만 어떤 레지스터 일반적으로 보유를 저장 해야 합니다.  예를 들어, 8 비트 레지스터만의 최저 8\-비트를 지정 된 값을 보유합니다.  이 8 비트 값이이 메서드에서 반환 되는 경우 64\-비트로 확장 됩니다.  
  
## 참고 항목  
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [CV\_HREG\_e 열거형](../../debugger/debug-interface-access/cv-hreg-e.md)
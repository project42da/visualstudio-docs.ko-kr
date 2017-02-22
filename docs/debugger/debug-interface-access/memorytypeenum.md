---
title: "MemoryTypeEnum | Microsoft Docs"
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
  - "MemoryTypeEnum 열거형"
ms.assetid: 8778c047-edeb-4495-8f9f-3f8bbb297099
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# MemoryTypeEnum
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

메모리에 액세스할 수 있는 형식을 지정 합니다.  
  
## 구문  
  
```cpp#  
enum MemoryTypeEnum {  
   MemTypeCode,  
   MemTypeData,  
   MemTypeStack,  
   MemTypeAny = -1  
};  
```  
  
#### 매개 변수  
 `MemTypeCode`  
 액세스 메모리 코드를.  
  
 `MemTypeData`  
 데이터 또는 스택 메모리에 액세스 합니다.  
  
 `MemTypeStack`  
 액세스는 메모리 스택.  
  
 `MemTypeAny`  
 모든 종류의 메모리에 액세스합니다.  
  
## 설명  
 이 열거형의 값으로 전달 되는 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md) 메서드가 서로 다른 유형의 메모리 액세스를 제한 합니다.  
  
## 요구 사항  
 헤더: cvconst.h  
  
## 참고 항목  
 [열거형 및 구조체](../../debugger/debug-interface-access/enumerations-and-structures.md)   
 [IDiaStackWalkHelper::readMemory](../../debugger/debug-interface-access/idiastackwalkhelper-readmemory.md)
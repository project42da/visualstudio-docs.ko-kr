---
title: "IDiaStackWalker::getEnumFrames2 | Microsoft Docs"
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
  - "IDiaStackWalker2::getEnumFrames2 메서드"
ms.assetid: 73196d3f-112c-4b3a-997b-7c6b815d4afc
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# IDiaStackWalker::getEnumFrames2
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

플랫폼 특정 형식에 대 한 스택 프레임 표시기를 검색합니다.  
  
## 구문  
  
```cpp#  
  
      HRESULT getEnumFrames2(   
   enum  CV_CPU_TYPE_e    cpuid,  
   IDiaStackWalkHelper*   pHelper,  
   IDiaEnumStackFrames**  ppEnum  
);  
```  
  
#### 매개 변수  
 `cpuid`  
 \[in\] 값은 [CV\_CPU\_TYPE\_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md) 플랫폼을 지정 하는 열거형을 합니다.  
  
 `pHelper`  
 \[in\] 도우미 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md) 개체입니다.  
  
 `ppEnum`  
 \[out\] 반환 된 [IDiaEnumStackFrames](../../debugger/debug-interface-access/idiaenumstackframes.md) 개체 목록이 포함 된 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md) 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 방금 x86 플랫폼에 대 한 스택 프레임 목록을 얻으려면 호출의 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md) 방법입니다.  
  
## 참고 항목  
 [IDiaStackWalker](../../debugger/debug-interface-access/idiastackwalker.md)   
 [CV\_CPU\_TYPE\_e 열거형](../../debugger/debug-interface-access/cv-cpu-type-e.md)   
 [IDiaStackWalkHelper](../../debugger/debug-interface-access/idiastackwalkhelper.md)   
 [IDiaStackFrame](../../debugger/debug-interface-access/idiastackframe.md)   
 [IDiaStackWalker::getEnumFrames](../../debugger/debug-interface-access/idiastackwalker-getenumframes.md)
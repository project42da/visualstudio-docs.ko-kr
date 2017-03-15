---
title: "IDebugProgram2::CanDetach | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::CanDetach"
helpviewer_keywords: 
  - "IDebugProgram2::CanDetach"
ms.assetid: dcd9ab6c-49e5-447e-aa7c-89f571f4a052
caps.latest.revision: 7
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 7
---
# IDebugProgram2::CanDetach
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

디버그 엔진 \(DE\) 프로그램에서 분리할 수 있습니다 경우 결정 합니다.  
  
## 구문  
  
```cpp#  
HRESULT CanDetach(  
   void  
);  
```  
  
```c#  
int CanDetach();  
```  
  
## 반환 값  
 경우 수 있습니다 분리, 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  반환 `S_FALSE` DE은 프로그램에서 분리할 수 없는 경우.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
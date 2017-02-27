---
title: "IDebugProgramDestroyEvent2::GetExitCode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramDestroyEvent2::GetExitCode"
helpviewer_keywords: 
  - "IDebugProgramDestroyEvent2::GetExitCode"
ms.assetid: 7f540cf6-e2d1-42b0-913e-a26d654b7659
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugProgramDestroyEvent2::GetExitCode
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램의 종료 코드를 가져옵니다.  
  
## 구문  
  
```cpp#  
HRESULT GetExitCode(   
   DWORD* pdwExit  
);  
```  
  
```c#  
int GetExitCode(   
   out uint pdwExit  
);  
```  
  
#### 매개 변수  
 `pdwExit`  
 \[out\] 프로그램의 종료 코드를 반환합니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 참고 항목  
 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)
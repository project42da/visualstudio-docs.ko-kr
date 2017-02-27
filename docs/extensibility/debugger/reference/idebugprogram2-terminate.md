---
title: "IDebugProgram2::Terminate | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::Terminate"
helpviewer_keywords: 
  - "IDebugProgram2::Terminate"
ms.assetid: 4d3127d3-b1e9-4b28-ac22-2f2eea255f86
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProgram2::Terminate
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

프로그램을 종료합니다.  
  
## 구문  
  
```cpp#  
HRESULT Terminate(   
   void   
);  
```  
  
```c#  
int Terminate();  
```  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 가능 하면 프로그램이 중지 되 고 언로드되는 과정에서. 그렇지 않으면 디버그 엔진 \(DE\) 이때 필요한 정리를 수행 합니다.  
  
 이 메서드 또는 [종료](../../../extensibility/debugger/reference/idebugprocess2-terminate.md) IDE를 일반적으로 모든 디버깅 중지 사용자에 대 한 응답으로 메서드를 호출 합니다.  이 메서드의 구현에 프로그램 프로세스 내에서 원칙적으로 종료 해야를 합니다.  이렇게 할 수 없는 경우는 DE 합니다 프로그램에서이 프로세스가 더 이상 실행 되지 않도록와 필요한 정리 작업을 수행할.  경우는 `IDebugProcess2::Terminate` 메서드는 IDE에서 호출 된, 잠시 후 전체 프로세스를 종료 합니다는 `IDebugProgram2::Terminate` 메서드가 호출 합니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [종료](../../../extensibility/debugger/reference/idebugprocess2-terminate.md)
---
title: "IDebugProgram2::GetProcess | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgram2::GetProcess"
helpviewer_keywords: 
  - "IDebugProgram2::GetProcess"
ms.assetid: 1d602485-ebaf-451c-9165-f2e226f20a90
caps.latest.revision: 13
caps.handback.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgram2::GetProcess
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 프로그램을 실행 하는 프로세스를 가져옵니다.  
  
## 구문  
  
```cpp  
HRESULT GetProcess(  
   IDebugProcess2** ppProcess  
);  
```  
  
```c#  
int GetProcess(  
   out IDebugProcess2 ppProcess  
);  
```  
  
#### 매개 변수  
 `ppProcess`  
 \[out\] 반환은 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md) 프로세스를 나타내는 인터페이스입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 디버그 엔진 \(DE\)를 구현 하지 않는 한은 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md) 인터페이스, DE의 구현은이 메서드를 항상 반환 해야 `E_NOTIMPL` 는 DE에, 즉 실행 되는 프로세스는이 메서드의 구현에 만족할 수 없습니다 확인할 수 없기 때문입니다.  
  
 구현 하는 `IDebugEngineLaunch2` 인터페이스는 DE; 프로세스를 만드는 방법을 알아야 한다는 것을 의미 따라서 DE의 구현에서 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스에서 실행 되는 프로세스를 알 수 있게 됩니다.  
  
## 참고 항목  
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugProcess2](../../../extensibility/debugger/reference/idebugprocess2.md)   
 [IDebugEngineLaunch2](../../../extensibility/debugger/reference/idebugenginelaunch2.md)
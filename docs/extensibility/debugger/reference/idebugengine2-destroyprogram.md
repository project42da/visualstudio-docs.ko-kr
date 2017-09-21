---
title: "IDebugEngine2::DestroyProgram | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugEngine2::DestroyProgram"
helpviewer_keywords: 
  - "IDebugEngine2::DestroyProgram"
ms.assetid: 0c9e2698-c70f-4770-a7bb-39650e9c3a1f
caps.latest.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 10
---
# IDebugEngine2::DestroyProgram
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

예외적인 지정한 프로그램이 종료 되 고 프로그램에 대 한 모든 참조는 DE 정리 해야는 디버그 엔진 \(DE\)을 알리고 프로그램 보내기 이벤트를 파괴 합니다.  
  
## 구문  
  
```cpp#  
HRESULT DestroyProgram(   
   IDebugProgram2* pProgram  
);  
```  
  
```cpp#  
int DestroyProgram(   
   IDebugProgram2 pProgram  
);  
```  
  
#### 매개 변수  
 `pProgram`  
 \[in\] [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 종료 되었습니다 예외적인 프로그램을 나타내는 개체입니다.  
  
## 반환 값  
 성공 하면 반환 `S_OK`. 그렇지 않으면 오류 코드를 반환 합니다.  
  
## 설명  
 이 메서드를 호출한 후에 DE 이후에 전송 된 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md) 세션 디버그 매니저 \(SDM\) 이벤트를 다시.  
  
 이 메서드가 구현 되지 않은 \(반환 `E_NOTIMPL`\)는 DE 디버깅 되는 프로그램은 동일한 프로세스에서 실행 하는 경우.  만 DE은 SDM와 동일한 프로세스에서 실행 되는 경우이 메서드는 구현 됩니다.  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)   
 [IDebugProgramDestroyEvent2](../../../extensibility/debugger/reference/idebugprogramdestroyevent2.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
---
title: "IEnumDebugThreads2 | Microsoft Docs"
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
  - "IEnumDebugThreads2"
helpviewer_keywords: 
  - "IEnumDebugThreads2"
ms.assetid: 1854f078-3b49-42c2-b65b-33e3b506fd63
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugThreads2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 interfac 디버그 세션에서 현재 실행 중인 스레드를 열거 합니다.  
  
## 구문  
  
```  
IEnumDebugThreads2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 프로그램에서 스레드의 목록을 나타내는 데이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md) 의 모든 스레드는 프로세스에서 실행 중인 모든 프로그램의 목록을 표시 합니다.이 인터페이스를 가져올 수 있습니다.  호출 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md) 목록에서 프로그램을 실행 하는 스레드를 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugThreads2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugthreads2-next.md)|열거 시퀀스에서 지정한 개수의 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugthreads2-skip.md)|열거 시퀀스에서 지정한 개수의 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugthreads2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugthreads2-clone.md)|현재 같은 열거 상태를 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugthreads2-getcount.md)|스레드 수를의 열거자를 가져옵니다.|  
  
## 설명  
 Visual Studio 일반적으로 업데이트 하기 위해이 인터페이스를 가져옵니다는  **스레드에서** 목록의 첫 번째 스레드가 호출에 얻을 윈도우 에서도 [실행](../../../extensibility/debugger/reference/idebugprocess3-execute.md), [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md), 및 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprocess2-enumthreads.md)   
 [EnumThreads](../../../extensibility/debugger/reference/idebugprogram2-enumthreads.md)   
 [단계](../../../extensibility/debugger/reference/idebugprocess3-step.md)   
 [계속](../../../extensibility/debugger/reference/idebugprocess3-continue.md)   
 [실행](../../../extensibility/debugger/reference/idebugprocess3-execute.md)
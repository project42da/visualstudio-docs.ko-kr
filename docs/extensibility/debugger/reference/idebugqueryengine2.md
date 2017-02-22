---
title: "IDebugQueryEngine2 | Microsoft Docs"
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
  - "IDebugQueryEngine2"
helpviewer_keywords: 
  - "IDebugQueryEngine2 인터페이스"
ms.assetid: 8f0e1838-a818-4459-9138-a3dceb7408de
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugQueryEngine2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에는 세션을 디버그 매니저 \(SDM\) 디버그 엔진 \(DE\)을 나타내는 인터페이스를 검색할 수 있습니다.  
  
## 구문  
  
```  
IDebugQueryEngine2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE DE 하는 가장 일반적인 인터페이스를 구현 하는 개체에이 인터페이스를 구현 \(같은 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md), [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md), 및 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)\) 액세스를 허용 하는 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md) DE 자체의 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 일반적인 DE 인터페이스이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugQueryEngine2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetEngineInterface](../../../extensibility/debugger/reference/idebugqueryengine2-getengineinterface.md)|사용자 지정 디버그 엔진 \(DE\) 인터페이스를 가져옵니다.|  
  
## 설명  
 이 인터페이스를 구현 하는 개체에서 일반적으로 구현 되는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인과 관계 정렬 기능을 통해; 단계별 실행을 지원 하기 위해 인터페이스 디버거 함수로 단계별로 실행 되 면, 실행 하는 다음 함수 위의 함수 스택의 있지만 함수는 다른 스레드의 완전히 수 있습니다.  참고 "인과 관계"의 정의 [Visual Studio 디버거 용어집](../../../extensibility/debugger/reference/visual-studio-debugger-glossary.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)   
 [IDebugThread2](../../../extensibility/debugger/reference/idebugthread2.md)   
 [IDebugStackFrame2](../../../extensibility/debugger/reference/idebugstackframe2.md)   
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
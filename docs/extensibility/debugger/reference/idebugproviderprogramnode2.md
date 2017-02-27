---
title: "IDebugProviderProgramNode2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProviderProgramNode2"
helpviewer_keywords: 
  - "IDebugProviderProgramNode2"
ms.assetid: f0bca1cc-afbe-44cf-b5aa-d078aa685d24
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugProviderProgramNode2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스를 인터페이스를 프로그램 관련 프로세스 경계에서 마샬링합니다.  
  
## 구문  
  
```  
IDebugProviderProgramNode2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\)를 구현 하는 동일한 개체에서이 인터페이스는 구현 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 프로세스 경계를 넘어 마샬링 인터페이스를 지원 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProgramNode2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  이 인터페이스를 가져올 수 없는 경우에 DE 인터페이스의 마샬링 지원 하지 않습니다.  
  
## 메서드에서 Vtable 순서  
 이 인터페이스에 다음 메서드를 구현합니다.  
  
|메서드|설명|  
|---------|--------|  
|[UnmarshalDebuggeeInterface](../../../extensibility/debugger/reference/idebugproviderprogramnode2-unmarshaldebuggeeinterface.md)|프로세스 경계에 걸쳐 특정된 인터페이스를 가져옵니다.|  
  
## 설명  
 DE은 별도 프로세스 공간에서 디버깅 중인 프로그램에서 실행 될 때이 인터페이스를 구현할 수: 예를 들어, 있는 DE입니다 실행할 때 Visual Studio 프로세스 공간을 디버깅 중인 프로그램의 프로세스 공간에서.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)
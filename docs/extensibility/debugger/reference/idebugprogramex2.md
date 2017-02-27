---
title: "IDebugProgramEx2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramEx2"
helpviewer_keywords: 
  - "IDebugProgramEx2 인터페이스"
ms.assetid: 663359ed-635a-4539-addb-0cc52f19d1bd
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# IDebugProgramEx2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에는 세션을 디버그 매니저 \(SDM\) 프로그램에 연결 하 고 프로그램과 연결 프로그램이 노드를 가져올 수 있습니다.  
  
## 구문  
  
```  
IDebugProgramEx2 : IUnknown  
```  
  
## 구현자 참고 사항  
 동일한 개체에서이 인터페이스를 구현 하는 사용자 지정 포트 공급자는 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스 포트 공급자 모든 세션을 추적할 수 있도록 하면서 동시에 프로그램을 연결 하는 SDM 수 있도록 프로그램에 첨부 된.  사용자 지정 포트 공급자는 선택한 경우이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 SDM 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProgram2` 인터페이스 프로그램에 연결 된 세션을 추적 하기 위해이 인터페이스를 얻을 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProgramEx2`.  
  
|메서드|설명|  
|---------|--------|  
|[연결](../../../extensibility/debugger/reference/idebugprogramex2-attach.md)|프로그램에 대 한 세션을 연결합니다.|  
|[GetProgramNode](../../../extensibility/debugger/reference/idebugprogramex2-getprogramnode.md)|프로그램과 연결 프로그램이 노드를 가져옵니다.|  
  
## 설명  
 이 인터페이스는 SDM 및 프로그램 간의 비공개입니다.  
  
## 요구 사항  
 헤더: Portpriv.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
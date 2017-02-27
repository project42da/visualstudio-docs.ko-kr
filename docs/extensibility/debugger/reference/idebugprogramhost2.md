---
title: "IDebugProgramHost2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugProgramHost2"
helpviewer_keywords: 
  - "IDebugProgramHost2 인터페이스"
ms.assetid: 2c37b3aa-97a9-4665-8709-edd917f18cb1
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# IDebugProgramHost2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 프로그램에 대 한 호스트 \(프로세스\) 정보를 제공합니다.  
  
## 구문  
  
```  
IDebugProgramHost2 : IUnknown  
```  
  
## 구현자 참고 사항  
 동일한 개체에서이 인터페이스를 구현 하는 디버그 엔진은 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md) 인터페이스는 호스팅 프로세스에 대 한 정보를 제공 합니다.  이 선택적 인터페이스입니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProgram2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProgramHost2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetHostName](../../../extensibility/debugger/reference/idebugprogramhost2-gethostname.md)|제목, 이름, 또는이 프로그램을 호스팅 프로세스의 파일 이름을 가져옵니다.|  
|[GetHostId](../../../extensibility/debugger/reference/idebugprogramhost2-gethostid.md)|이 프로그램의 호스팅 프로세스의 프로세스 id를 가져옵니다.|  
|[GetHostMachineName](../../../extensibility/debugger/reference/idebugprogramhost2-gethostmachinename.md)|호스팅 프로세스를이 프로그램을 실행 중인 컴퓨터의 이름을 가져옵니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgram2](../../../extensibility/debugger/reference/idebugprogram2.md)
---
title: "IDebugProgramEngines2 | Microsoft Docs"
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
  - "IDebugProgramEngines2"
helpviewer_keywords: 
  - "IDebugProgramEngines2 인터페이스"
ms.assetid: 53d648f0-6c11-4337-badd-c43f3872b62c
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugProgramEngines2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스 프로그램 노드에서이 프로그램을 디버깅할 수 있는 모든 가능한 디버그 엔진 \(DE\)를 지정할 수 있습니다.  
  
## 구문  
  
```  
IDebugProgramEngines2 : IUnknown  
```  
  
## 구현자 참고 사항  
 DE 또는 사용자 지정 포트 공급자를 구현 하는 동일한 개체에서이 인터페이스를 구현 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md) 특정 프로그램을 사용 하 여 특정 DE 구축을 지원 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [QueryInterface](/visual-cpp/atl/queryinterface) 에 있는 `IDebugProgramNode2` 이 인터페이스를 가져올 수 있는 인터페이스입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugProgramEngines2`.  
  
|메서드|설명|  
|---------|--------|  
|[EnumPossibleEngines](../../../extensibility/debugger/reference/idebugprogramengines2-enumpossibleengines.md)|이 프로그램을 디버깅 하는 모든 가능한 Des를 나타냅니다.|  
|[SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md)|이 프로그램을 디버깅 하는 데 사용 하는 DE를 선택 합니다.|  
  
## 설명  
 DE은 사용자가 선택 되 면, 원하는 프로그램이 노드를 호출 하 여 등록 된 [SetEngine](../../../extensibility/debugger/reference/idebugprogramengines2-setengine.md).  선택한 엔진에서 반환 하는 엔진이 됩니다 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md).  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugProgramNode2](../../../extensibility/debugger/reference/idebugprogramnode2.md)   
 [GetEngineInfo](../../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md)
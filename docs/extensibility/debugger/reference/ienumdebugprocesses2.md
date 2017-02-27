---
title: "IEnumDebugProcesses2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugProcesses2"
helpviewer_keywords: 
  - "IEnumDebugProcesses2"
ms.assetid: 06a1368f-10f0-44eb-af61-e388c2327111
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IEnumDebugProcesses2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 포트에서 실행 중인 프로세스를 열거 합니다.  
  
## 구문  
  
```  
IEnumDebugProcesses : IUnknown  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트 공급자는 포트에서 실행 되는 프로세스를 제공 하려면이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 Visual Studio [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md) 이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugProcesses2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugprocesses2-next.md)|프로세스 열거 시퀀스에서 지정 된 수를 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugprocesses2-skip.md)|프로세스 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugprocesses2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugprocesses2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugprocesses2-getcount.md)|프로세스를의 열거자를 가져옵니다.|  
  
## 설명  
 Visual Studio이 인터페이스를 사용 하 여 채우기의  **프로세스** 창입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)
---
title: "IEnumDebugPorts2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugPorts2"
helpviewer_keywords: 
  - "IEnumDebugPorts2"
ms.assetid: 1754eef3-cf62-42e0-b218-1911acba77d4
caps.latest.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 12
---
# IEnumDebugPorts2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 컴퓨터 또는 포트 협력 업체의 포트 열거합니다.  
  
## 구문  
  
```  
IEnumDebugPorts2 : IUnknown  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트 협력 업체는 협력 업체에서 만든 포트의 목록을 나타내는 데이 인터페이스를 구현 합니다.  Visual Studio 포트 공급 업체 지원에이 인터페이스를 구현합니다.  
  
## 호출자에 대 한 참고 사항  
 호출 [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md) 포트 공급자가 만든 포트 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  호출 [EnumPersistedPorts](../../../extensibility/debugger/reference/idebugportsupplier3-enumpersistedports.md) 에 저장 된 포트 목록을 나타내는이 인터페이스를 가져올 수 디스크에 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugPorts2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugports2-next.md)|포트 열거 시퀀스에서 지정 된 수를 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugports2-skip.md)|포트 열거 시퀀스에서 지정 된 수를 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugports2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugports2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugports2-getcount.md)|포트 번호를의 열거자를 가져옵니다.|  
  
## 설명  
 Visual Studio이 인터페이스를 사용 하 여 프로세스에 연결을 사용 하는 포트 목록을 채울 수 있도록 합니다.  
  
 일반적으로 디버그 엔진은이 인터페이스를 사용 하지 않습니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugcoreserver2-enumports.md)   
 [EnumPorts](../../../extensibility/debugger/reference/idebugportsupplier2-enumports.md)
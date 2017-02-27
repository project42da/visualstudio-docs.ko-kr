---
title: "IDebugPort2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPort2"
helpviewer_keywords: 
  - "IDebugPort2 인터페이스"
ms.assetid: 8fd87f05-a950-4d14-b925-98be29d4facc
caps.latest.revision: 13
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 13
---
# IDebugPort2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 디버그 포트를 컴퓨터를 나타냅니다.  
  
## 구문  
  
```  
IDebugPort2 : IUnknown  
```  
  
## 구현자 참고 사항  
 사용자 지정 포트 공급자 컴퓨터에 디버그 포트를 나타내는 데이 인터페이스를 구현 합니다.  
  
 송신 포트 이벤트 기능을 지 원하는 포트도 구현 해야는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 지 원하는 인터페이스는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 를 차례로 제공 하는 인터페이스는 [IDebugPortEvents2](../../../extensibility/debugger/reference/idebugportevents2.md) 인터페이스.  
  
## 호출자에 대 한 참고 사항  
 호출 하려면 [GetPort](../../../extensibility/debugger/reference/idebugportsupplier2-getport.md) 또는 [포트 추가](../../../extensibility/debugger/reference/idebugportsupplier2-addport.md) 요청 된 포트를 표시 합니다.이 인터페이스를 반환 합니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPort2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetPortName](../../../extensibility/debugger/reference/idebugport2-getportname.md)|포트 이름을 반환합니다.|  
|[GetPortId](../../../extensibility/debugger/reference/idebugport2-getportid.md)|포트 식별자를 반환합니다.|  
|[GetPortRequest](../../../extensibility/debugger/reference/idebugport2-getportrequest.md)|\(사용 가능한 경우\) 포트를 만드는 데 사용 되는 요청을 반환 합니다.|  
|[GetPortSupplier](../../../extensibility/debugger/reference/idebugport2-getportsupplier.md)|이 포트에 대해 포트 공급자를 반환합니다.|  
|[GetProcess](../../../extensibility/debugger/reference/idebugport2-getprocess.md)|프로세스의 식별자를 지정 하는 프로세스를 인터페이스를 반환 합니다.|  
|[EnumProcesses](../../../extensibility/debugger/reference/idebugport2-enumprocesses.md)|포트에서 실행 중인 모든 프로세스를 열거 합니다.|  
  
## 설명  
 로컬 포트 프로세스와 로컬 컴퓨터에서 실행 되는 프로그램에 대 한 액세스를 제공 합니다.  다른 포트는 Windows CE 기반 장치를 직렬 케이블 연결 또는 비 DCOM 컴퓨터에 네트워크 연결을 나타낼 수 있습니다.  `IDebugPort2` 인터페이스 이름과 식별자는 포트는 포트에서 실행 중인 모든 프로세스를 열거를 찾고 시작 하 고 포트에서 프로세스 종료에 대 한 기능을 제공 하는 데 사용 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPortSupplier2](../../../extensibility/debugger/reference/idebugportsupplier2.md)   
 [IDebugCoreServer2](../../../extensibility/debugger/reference/idebugcoreserver2.md)
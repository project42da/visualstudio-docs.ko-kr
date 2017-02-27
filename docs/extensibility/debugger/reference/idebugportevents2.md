---
title: "IDebugPortEvents2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDebugPortEvents2"
helpviewer_keywords: 
  - "IDebugPortEvents2 인터페이스"
ms.assetid: 2c017094-3ba2-4067-83f9-147df1d96bce
caps.latest.revision: 18
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 18
---
# IDebugPortEvents2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스의 프로세스 및 프로그램 생성과 소멸을 특정 포트에서 수신기를 \(일반적으로 세션 디버그 관리자 \[SDM\] 또는 디버그 엔진\)에 알립니다.  이 정보를 사용 하 여 포트에서 실행 되는 프로그램 및 프로세스에 대 한 실시간 뷰를 제공 될 수 있습니다.  
  
## 구문  
  
```  
IDebugPortEvents2 : IUnknown  
```  
  
## 구현자 참고 사항  
 Visual Studio 일반적으로 프로그램의 생성 및 소멸에 대 한 알림을 받으려면이 인터페이스를 구현 합니다.  디버그 엔진 이러한 포트 이벤트를 수신 대기 하기 위해이 인터페이스를 구현할 수도 있습니다.  
  
## 호출자에 대 한 참고 사항  
 모든 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md) 인터페이스를 쿼리할 수 있는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 인터페이스입니다.  다음은 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer.FindConnectionPoint%2A> 메서드에 대 한 `IDebugPortEvents2` 호출 되는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPointContainer> 인터페이스를 가져올 수는 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 인터페이스.  마지막으로 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint.Advise%2A> 메서드에서 <xref:System.Runtime.InteropServices.ComTypes.IConnectionPoint> 인터페이스 이벤트를 통해 보내는 호출의 [이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md) 메서드.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugPortEvents2`.  
  
|메서드|설명|  
|---------|--------|  
|[이벤트](../../../extensibility/debugger/reference/idebugportevents2-event.md)|생성 및 폐기 하는 프로세스 및 프로그램에서 포트를 설명 하는 이벤트를 전송 합니다.|  
  
## 설명  
 `IDebugPortEvents2`또한 SDM에서 이미 디버깅 되는 프로세스에서 실행 되는 프로그램을 디버깅 하려면 사용 됩니다.  
  
 포트 이벤트에는 SDM이이 인터페이스에서 전달 됩니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [IDebugPort2](../../../extensibility/debugger/reference/idebugport2.md)
---
title: "IEnumDebugBoundBreakpoints2 | Microsoft Docs"
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
  - "IEnumDebugBoundBreakpoints2"
helpviewer_keywords: 
  - "IEnumDebugBoundBreakpoints2"
ms.assetid: ea03e7e1-28d6-40b7-8097-bbb61d3b7caa
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IEnumDebugBoundBreakpoints2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에 바인딩된 중단점을 보류 중단점에 관련 된 열거 또는 이벤트 중단점을 바인딩할.  
  
## 구문  
  
```  
IEnumDebugBoundBreakpoints2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  중단점 지원 되는 경우이 인터페이스를 구현 해야 합니다.  
  
## 호출자에 대 한 참고 사항  
 Visual Studio 호출합니다.  
  
-   [EnumBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointevent2-enumbreakpoints.md)발생 된 모든 중단점의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
-   [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)연결 된 모든 중단점의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
-   [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)해당 보류 중단점과 바인딩된 모든 중단점의 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugBoundBreakpoints2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-next.md)|지정한 수 만큼 열거 시퀀스에서 바인딩된 중단점을 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-skip.md)|지정한 수 만큼 열거 시퀀스에서 바인딩된 중단점을 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugboundbreakpoints2-getcount.md)|수가 바인딩된 중단점의 열거자를 가져옵니다.|  
  
## 설명  
 Visual Studio이 인터페이스로 표시 되는 바인딩된 중단점을 사용 하 여 IDE에서 중단점의 표시를 업데이트 합니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugbreakpointboundevent2-enumboundbreakpoints.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)   
 [EnumBoundBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumboundbreakpoints.md)
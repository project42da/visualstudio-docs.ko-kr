---
title: "IDebugErrorBreakpoint2 | Microsoft Docs"
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
  - "IDebugErrorBreakpoint2"
helpviewer_keywords: 
  - "IDebugErrorBreakpoint2 인터페이스"
ms.assetid: 1f2a4b94-3713-46e9-8272-3917187792bd
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugErrorBreakpoint2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에 오류 또는 잘못 된 위치, 잘못 된 식을 보류 중단점 \(코드를 로드할 없습니다 아직 등\) 연결 되어 없는 않은 이유 같은 경고 중단점을 나타냅니다.  
  
## 구문  
  
```  
IDebugErrorBreakpoint2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  이 인터페이스는 중단점이 바인딩 문제를 보고 하려면 사용 됩니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md) 이 인터페이스를 가져옵니다.  이 인터페이스는 또한 반환 될 수 있습니다 \(표시 되는 목록의 일부로 [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md) 인터페이스\)를 호출 하 여 [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) 또는 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md).  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugErrorBreakpoint2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetPendingBreakpoint](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getpendingbreakpoint.md)|오류가 발생 한 보류 중인 중단점을 가져옵니다.|  
|[GetBreakpointResolution](../../../extensibility/debugger/reference/idebugerrorbreakpoint2-getbreakpointresolution.md)|오류를 설명 하는 중단점 오류 해상도를 가져옵니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugBreakpointErrorEvent2](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2.md)   
 [GetErrorBreakpoint](../../../extensibility/debugger/reference/idebugbreakpointerrorevent2-geterrorbreakpoint.md)   
 [IEnumDebugErrorBreakpoints2](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2.md)   
 [다음](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)   
 [IDebugPendingBreakpoint2](../../../extensibility/debugger/reference/idebugpendingbreakpoint2.md)   
 [IDebugErrorBreakpointResolution2](../../../extensibility/debugger/reference/idebugerrorbreakpointresolution2.md)
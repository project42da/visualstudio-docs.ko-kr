---
title: "IEnumDebugErrorBreakpoints2 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IEnumDebugErrorBreakpoints2"
helpviewer_keywords: 
  - "IEnumDebugErrorBreakpoints2"
ms.assetid: ffdad73d-969a-45ef-9ad1-7f5d3b814018
caps.latest.revision: 9
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 9
---
# IEnumDebugErrorBreakpoints2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스에는 보류 중단점에 연관 된 오류 중단점 열거 합니다.  
  
## 구문  
  
```  
IEnumDebugErrorBreakpoints2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 중단점에 대 한 지원의 일부로 서이 인터페이스를 구현합니다.  
  
## 호출자에 대 한 참고 사항  
 Visual Studio 호출 [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md) 은 바인딩할 수 없습니다, 중단점을 나타내는이 인터페이스를 가져올 수 또는 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md) 바인딩되지 않습니다 중단점 목록을 나타내는이 인터페이스를 가져올 수 있습니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IEnumDebugErrorBreakpoints2`.  
  
|메서드|설명|  
|---------|--------|  
|[다음](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-next.md)|지정한 수 만큼 열거 시퀀스에서 오류 중단점을 검색합니다.|  
|[Skip](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-skip.md)|지정한 수 만큼 열거 시퀀스에서 오류 중단점을 건너뜁니다.|  
|[다시 설정](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-reset.md)|열거형 시퀀스를 처음으로 다시 설정합니다.|  
|[복제](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-clone.md)|현재 열거자와 열거 상태가 같은 포함 하는 열거자를 만듭니다.|  
|[GetCount](../../../extensibility/debugger/reference/ienumdebugerrorbreakpoints2-getcount.md)|번호를의 오류 중단점의 열거자를 가져옵니다.|  
  
## 설명  
 이 인터페이스의 목록을 보유 하 고 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md) 인터페이스는 수 바인딩할 수 없는 이유는 그 수 없습니다 바운드 될 중단점을 각각 설명 합니다.  Visual Studio 사용 하는 `IEnumDebugErrorBreakpoint2` IDE에 표시 되는 중단점을 업데이트 하는 인터페이스입니다.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [CanBind](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-canbind.md)   
 [EnumErrorBreakpoints](../../../extensibility/debugger/reference/idebugpendingbreakpoint2-enumerrorbreakpoints.md)   
 [IDebugErrorBreakpoint2](../../../extensibility/debugger/reference/idebugerrorbreakpoint2.md)
---
title: "IDebugModule2 | Microsoft Docs"
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
  - "IDebugModule2"
helpviewer_keywords: 
  - "IDebugModule2 인터페이스"
ms.assetid: 24c2a126-f4ab-4891-8509-8ef99b994c08
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugModule2
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

이 인터페이스는 모듈을 나타냅니다\-프로그램에서 실행 가능한 단위, 즉\-DLL 같은.  
  
## 구문  
  
```  
IDebugModule2 : IUnknown  
```  
  
## 구현자 참고 사항  
 디버그 엔진 \(DE\) 나타내는 모듈 및 해당 모듈에 대 한 정보에 액세스 합니다이 인터페이스를 구현 합니다.  
  
## 호출자에 대 한 참고 사항  
 호출을 [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md) 이 인터페이스를 반환 합니다.  DE 센드는 [IDebugModuleLoadEvent2](../../../extensibility/debugger/reference/idebugmoduleloadevent2.md) 인터페이스를 사용 하 여 세션 디버그 매니저 \(SDM\)에 있는 [이벤트](../../../extensibility/debugger/reference/idebugeventcallback2-event.md) 메서드.  
  
 이 인터페이스를 반환할 수 있습니다는 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md) 구조 \(호출 하 여 반환 된 [EnumFrameInfo](../../../extensibility/debugger/reference/idebugthread2-enumframeinfo.md)\).  
  
 [다음](../../../extensibility/debugger/reference/ienumdebugmodules2-next.md)또한이 인터페이스를 반환 \([EnumModules](../../../extensibility/debugger/reference/idebugprogram2-enummodules.md) 반환의 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md) 인터페이스\)입니다.  
  
## 메서드에서 Vtable 순서  
 다음 표에서 메서드를 `IDebugModule2`.  
  
|메서드|설명|  
|---------|--------|  
|[GetInfo](../../../extensibility/debugger/reference/idebugmodule2-getinfo.md)|가져옵니다는 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md) 이 모듈에 설명 합니다.|  
|[ReloadSymbols\_Deprecated](../../../extensibility/debugger/reference/idebugmodule2-reloadsymbols-deprecated.md)|사용 되지 않음.  사용 하지 않습니다.  이 모듈에 대 한 기호를 다시 로드합니다.|  
  
## 설명  
 모듈 정보를 표시할 수 있는  **모듈** ide 창.  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [코어 인터페이스](../../../extensibility/debugger/reference/core-interfaces.md)   
 [MODULE\_INFO](../../../extensibility/debugger/reference/module-info.md)   
 [GetModule](../../../extensibility/debugger/reference/idebugmoduleloadevent2-getmodule.md)   
 [FRAMEINFO](../../../extensibility/debugger/reference/frameinfo.md)   
 [IEnumDebugModules2](../../../extensibility/debugger/reference/ienumdebugmodules2.md)
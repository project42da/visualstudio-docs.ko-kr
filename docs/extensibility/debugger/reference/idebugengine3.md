---
title: "IDebugEngine3 | Microsoft Docs"
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
  - "IDebugEngine3"
helpviewer_keywords: 
  - "IDebugEngine3 인터페이스"
ms.assetid: 8bdf4bb7-3b5d-4991-8981-772d4f6bb656
caps.latest.revision: 15
caps.handback.revision: 15
ms.author: "gregvanl"
manager: "ghogen"
---
# IDebugEngine3
[!INCLUDE[vs2017banner](../../../code-quality/includes/vs2017banner.md)]

하나 이상의 모듈의 디버깅을 제어 하는 단일 디버그 엔진을 \(DE\)를 나타냅니다.  
  
## 구문  
  
```  
IDebugEngine3 : IDebugEngine2  
```  
  
## 구현자 참고 사항  
 \(기호 지 원하는 경우\)이이 인터페이스는 사용자 지정 DE에서 JustMyCode 상태를 사용할 수 있도록 구현 됩니다.  기호 및 Justmycode를 지 원하는 경우이 인터페이스는 DE에서 구현 되어야 합니다.  
  
## 호출자에 대 한 참고 사항  
 이 인터페이스는 세션 디버그 매니저 \(SDM\) 사용자 옵션에 대 한 위치에서 기호 로드를 전달 하 여 호출 됩니다.  또한 엔진의 GUID가 인스턴스화될 때 설정 하려면 호출 됩니다 \(이 GUID 메트릭 엔진 등록을 기반으로\).  또한 SDM은 JustMyCode 상태를 설정 하 고 디버거에서 지정된 된 상태에 의해 알려진 모든 예외를 설정 하려면이 인터페이스를 호출 합니다.  
  
## 메서드에서 Vtable 순서  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)에서 상속되는 메서드 외에 `IDebugEngine3` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[SetSymbolPath](../../../extensibility/debugger/reference/idebugengine3-setsymbolpath.md)|디버깅 기호를 검색 하는 DE 사용 합니다 경로 또는 경로 설정 합니다.|  
|[LoadSymbols](../../../extensibility/debugger/reference/idebugengine3-loadsymbols.md)|아직 해당 기호가 로드 되어 있지 않은 모든 모듈에 대 한 기호를 로드 합니다.|  
|[SetJustMyCodeState](../../../extensibility/debugger/reference/idebugengine3-setjustmycodestate.md)|DE JustMyCode 정보를 알려 줍니다.|  
|[SetEngineGuid](../../../extensibility/debugger/reference/idebugengine3-setengineguid.md)|DE GUID의 메트릭을 설정합니다.|  
|[SetAllExceptions](../../../extensibility/debugger/reference/idebugengine3-setallexceptions.md)|모든 예외 처리 중인 현재 지정된 된 상태를 설정 합니다.|  
  
## 요구 사항  
 헤더: msdbg.h  
  
 네임 스페이스: Microsoft.VisualStudio.Debugger.Interop  
  
 어셈블리: Microsoft.VisualStudio.Debugger.Interop.dll  
  
## 참고 항목  
 [IDebugEngine2](../../../extensibility/debugger/reference/idebugengine2.md)
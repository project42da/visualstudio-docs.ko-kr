---
title: "연결 및 프로그램을 분리 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로그램에 연결 되는 디버그 엔진"
  - "프로그램에서 분리 되는 디버그 엔진"
ms.assetid: 79dcbb9b-c7f8-40fc-8a00-f37fe1934f51
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 연결 및 프로그램을 분리 합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 연결 메서드 및 속성을 사용 하 여 이벤트의 순서를 보내는 필요 합니다.  
  
## 메서드 및 이벤트의 순서  
  
1.  세션 디버그 매니저 \(SDM\)를 호출 하 여 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드.  
  
     디버그 엔진 \(DE\) 프로세스 모델을 기반으로 `IDebugProgramNodeAttach2::OnAttach` 메서드가 다음 할 일을 결정 하는 다음 방법 중 하나를 반환 합니다.  
  
     경우 `S_FALSE` 반환 디버그 엔진 성공적으로 프로그램에 연결 되었습니다.  그렇지 않은 경우는 [연결](../../extensibility/debugger/reference/idebugengine2-attach.md) 메서드를 호출할 연결 프로세스를 완료 합니다.  
  
     경우 `S_OK` 반환의 DE 되는 SDM와 같은 프로세스에 로드 되도록 합니다.  SDM은 다음과 같은 작업을 수행합니다.  
  
    1.  호출 [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) 는 DE의 엔진 정보를 합니다.  
  
    2.  DE co\-creates.  
  
    3.  [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)를 호출합니다.  
  
2.  DE 센드는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
3.  DE 센드는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
4.  DE 센드는 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) SDM을 하는 `EVENT_SYNC_STOP` 특성입니다.  
  
 프로그램에서 분리를 두 단계 프로세스입니다.  
  
1.  SDM 호출 [Detach](../../extensibility/debugger/reference/idebugprogram2-detach.md).  
  
2.  DE 센드는 [IDebugProgramDestroyEvent2](../../extensibility/debugger/reference/idebugprogramdestroyevent2.md).  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)
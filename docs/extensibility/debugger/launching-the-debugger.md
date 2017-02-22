---
title: "디버거 시작 | Microsoft Docs"
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
  - "디버거 시작, 디버깅 [디버깅 SDK]"
  - "디버거 [디버깅 SDK] 시작"
ms.assetid: f24da1a1-f923-48b4-989f-18a22b581d1b
caps.latest.revision: 11
caps.handback.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
---
# 디버거 시작
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

디버거 메서드 및 적절 한 특성을 사용 하 여 이벤트의 순서를 보내는 필요 합니다.  
  
## 메서드 및 이벤트의 시퀀스  
  
1.  세션 디버그 매니저 \(SDM\)를 선택 하 여 호출 되는  **디버그** 메뉴 및 선택 하 고  **시작**.  자세한 내용은 [프로그램 실행](../../extensibility/debugger/launching-a-program.md)를 참조하십시오.  
  
2.  SDM 호출 [OnAttach](../../extensibility/debugger/reference/idebugprogramnodeattach2-onattach.md) 메서드가 있습니다.  
  
3.  디버그 엔진 \(DE\) 프로세스 모델을 기반으로 `IDebugProgramNodeAttach2::OnAttach` 메서드가 다음 할 일을 결정 하는 다음 방법 중 하나를 반환 합니다.  
  
     경우 `S_FALSE` 반환 \(DE\) 디버그 엔진입니다 가상 머신 프로세스에 로드 되도록 합니다.  
  
     또는  
  
     경우 `S_OK` 반환은 DE입니다 로드 하는 SDM의 과정에 있습니다.  SDM은 다음 작업을 수행 하는 다음:  
  
    1.  호출 [GetEngineInfo](../../extensibility/debugger/reference/idebugprogramnode2-getengineinfo.md) 는 DE의 엔진 정보를 합니다.  
  
    2.  DE co\-creates.  
  
    3.  [연결](../../extensibility/debugger/reference/idebugengine2-attach.md)를 호출합니다.  
  
4.  DE 센드는 [IDebugEngineCreateEvent2](../../extensibility/debugger/reference/idebugenginecreateevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
5.  DE 센드는 [IDebugProgramCreateEvent2](../../extensibility/debugger/reference/idebugprogramcreateevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
6.  DE 센드는 [IDebugThreadCreateEvent2](../../extensibility/debugger/reference/idebugthreadcreateevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
7.  DE 센드는 [IDebugLoadCompleteEvent2](../../extensibility/debugger/reference/idebugloadcompleteevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
8.  DE 센드는 [IDebugEntryPointEvent2](../../extensibility/debugger/reference/idebugentrypointevent2.md) SDM을 하는 `EVENT_SYNC` 특성입니다.  
  
## 참고 항목  
 [호출 디버거 이벤트](../../extensibility/debugger/calling-debugger-events.md)   
 [프로그램 실행](../../extensibility/debugger/launching-a-program.md)
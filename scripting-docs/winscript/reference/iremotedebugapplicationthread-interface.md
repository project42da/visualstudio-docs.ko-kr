---
title: "IRemoteDebugApplicationThread 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IRemoteDebugApplicationThread 인터페이스"
ms.assetid: 062bb997-7b9e-4945-bfbe-d5b92d5cb707
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# IRemoteDebugApplicationThread 인터페이스
특정 응용 프로그램 내의 실행 스레드를 나타냅니다.  
  
 `IUnknown`에서 상속되는 메서드 외에 `IRemoteDebugApplicationThread` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IRemoteDebugApplicationThread::GetSystemThreadId](../../winscript/reference/iremotedebugapplicationthread-getsystemthreadid.md)|스레드와 관련 된 운영 system–dependent 식별자를 반환 합니다.|  
|[IRemoteDebugApplicationThread::GetApplication](../../winscript/reference/iremotedebugapplicationthread-getapplication.md)|이 스레드와 연관 된 응용 프로그램 개체를 반환 합니다.|  
|[IRemoteDebugApplicationThread::EnumStackFrames](../../winscript/reference/iremotedebugapplicationthread-enumstackframes.md)|이 스레드와 연관 된 스택 프레임에 대 한 열거자를 반환 합니다.|  
|[IRemoteDebugApplicationThread::GetDescription](../../winscript/reference/iremotedebugapplicationthread-getdescription.md)|설명 및이 스레드의 상태를 가져옵니다.|  
|[IRemoteDebugApplicationThread::SetNextStatement](../../winscript/reference/iremotedebugapplicationthread-setnextstatement.md)|지정 된 프레임의 컨텍스트 내에서 코드를 지정 된 컨텍스트를 최대한 가깝게 계속 강제로 실행.|  
|[IRemoteDebugApplicationThread::GetState](../../winscript/reference/iremotedebugapplicationthread-getstate.md)|이 스레드의 상태를를 가져옵니다.|  
|[IRemoteDebugApplicationThread::Suspend](../../winscript/reference/iremotedebugapplicationthread-suspend.md)|스레드를 일시 중단 합니다.|  
|[IRemoteDebugApplicationThread::Resume](../../winscript/reference/iremotedebugapplicationthread-resume.md)|스레드를 다시 시작 합니다.|  
|[IRemoteDebugApplicationThread::GetSuspendCount](../../winscript/reference/iremotedebugapplicationthread-getsuspendcount.md)|스레드의 일시 중단 계수를 반환합니다.|
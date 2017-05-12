---
title: "IDebugApplicationThread 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationThread 인터페이스"
ms.assetid: f869c328-4409-4b74-a6c3-9e63fc58c63d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationThread 인터페이스
언어 엔진과 호스트 스레드 동기화를 제공 하 고 특정 스레드의 디버그 상태 정보를 유지할 수 있습니다.  이 인터페이스의 확장은 `IRemoteDebugApplicationThread` 스레드가 원격으로 액세스할 수 있도록 인터페이스.  
  
 `IRemoteDebugApplicationThread`에서 상속되는 메서드 외에 `IDebugApplicationThread` 인터페이스는 다음 메서드를 노출합니다.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplicationThread::SynchronousCallIntoThread](../../winscript/reference/idebugapplicationthread-synchronouscallintothread.md)|호출자가 응용 프로그램 스레드에서 코드를 실행 하기 위한 메커니즘을 제공 합니다.|  
|[IDebugApplicationThread::QueryIsCurrentThread](../../winscript/reference/idebugapplicationthread-queryiscurrentthread.md)|이 스레드에서 현재 실행 중인 스레드가 있는지 확인 합니다.|  
|[IDebugApplicationThread::QueryIsDebuggerThread](../../winscript/reference/idebugapplicationthread-queryisdebuggerthread.md)|이 스레드 디버거 스레드가 있는지 확인 합니다.|  
|[IDebugApplicationThread::SetDescription](../../winscript/reference/idebugapplicationthread-setdescription.md)|이 스레드에 대 한 설명을 설정합니다.|  
|[IDebugApplicationThread::SetStateString](../../winscript/reference/idebugapplicationthread-setstatestring.md)|스레드 상태에 대 한 설명을 설정합니다.|
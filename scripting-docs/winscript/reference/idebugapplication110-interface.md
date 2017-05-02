---
title: "IDebugApplication110 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplication110 인터페이스"
ms.assetid: ae943133-eb65-4ddc-a29f-9280a82dd8d6
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IDebugApplication110 인터페이스
`IDebugApplication110` 인터페이스 기능을 확장 하는 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md).  구현에서 Queryinterface를 호출 하 여이 인터페이스의 인스턴스를 가져올 수 있습니다 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md).  
  
> [!IMPORTANT]
>  V11.0 PDM 및 큰이 인터페이스를 구현 합니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IDebugApplication110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IDebugApplication110::SynchronousCallInMainThread](../../winscript/reference/idebugapplication110-synchronouscallinmainthread.md)|주 스레드에서 동기 호출 합니다.|  
|[IDebugApplication110::AsynchronousCallInMainThread](../../winscript/reference/idebugapplication110-asynchronouscallinmainthread.md)|주 스레드에서 비동기 호출을 만듭니다.|  
|[IDebugApplication110::CallableWaitForHandles](../../winscript/reference/idebugapplication110-callablewaitforhandles.md)|대기 하면서 신호를 받도록 지정 된 핸들에 대 한 호출이이 스레드에 게시 하는 데 스레드 간.  디버거 스레드에서이 메서드를 호출 해야 합니다.|
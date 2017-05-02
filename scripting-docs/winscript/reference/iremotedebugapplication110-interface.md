---
title: "IRemoteDebugApplication110 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IRemoteDebugApplication110 인터페이스"
ms.assetid: 785ab46a-8827-41cb-806a-132e6b2c8f47
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IRemoteDebugApplication110 인터페이스
호출자 프로세스에서 스크립트 디버거를 호출 하 고 새 기능을 제공 하는 데 사용 합니다.  
  
> [!IMPORTANT]
>  V11.0 PDM 및 큰이 인터페이스를 구현 합니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IRemoteDebugApplication110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IRemoteDebugApplication110::SetDebuggerOptions](../../winscript/reference/iremotedebugapplication110-setdebuggeroptions.md)|디버거 옵션을 업데이트 하기 위해 호출 됩니다.  0 \(SDO\_NONE\) 옵션 기본입니다.|  
|[IRemoteDebugApplication110::GetCurrentDebuggerOptions](../../winscript/reference/iremotedebugapplication110-getcurrentdebuggeroptions.md)|현재 사용할 수 있는 옵션 집합을 반환 합니다.|  
|[IRemoteDebugApplication110::GetMainThread](../../winscript/reference/iremotedebugapplication110-getmainthread.md)|주 스레드에서 호출 SetSite 호스트에 반환 합니다.|
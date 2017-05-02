---
title: "IRemoteDebugApplication110::GetMainThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IRemoteDebugApplication110::GetMainThread"
ms.assetid: 9982acc9-3d35-4dcf-8ca9-662469de4072
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IRemoteDebugApplication110::GetMainThread
주 스레드를 호출 하는 호스트에 대 한 반환 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439), 그렇지 않으면 E\_FAIL을 반환 합니다.  
  
> [!IMPORTANT]
>  [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT GetMainThread([out] IRemoteDebugApplicationThread **ppThread);  
  
```  
  
#### 매개 변수  
 `ppThread`  
 \[out\] The main [IRemoteDebugApplicationThread 인터페이스](../../winscript/reference/iremotedebugapplicationthread-interface.md).  
  
## 참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)   
 [IRemoteDebugApplication110 인터페이스](../../winscript/reference/iremotedebugapplication110-interface.md)
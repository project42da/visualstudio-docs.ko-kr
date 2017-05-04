---
title: "IDebugApplicationThread110::IsSuspendedForBreakPoint | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationThread110::IsSuspendedForBreakPoint"
ms.assetid: 60688222-557f-4a43-a19b-846cee393cd0
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IDebugApplicationThread110::IsSuspendedForBreakPoint
결정 여부 [IDebugApplicationThreadEvents110::OnSuspendForBreakPoint](../../winscript/reference/idebugapplicationthreadevents110-onsuspendforbreakpoint.md) 이 스레드에서 호출 되 고 아직 완료 되지 않았습니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT IsSuspendedForBreakPoint([out, annotation("_Out_")] BOOL * pfIsSuspended);  
```  
  
#### 매개 변수  
 `pfIsSuspended`  
 \[out\] `true` 스레드가 중단점에 대 한, 그렇지 않으면 일시 경우 `false`.  
  
## 참고 항목  
 [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)
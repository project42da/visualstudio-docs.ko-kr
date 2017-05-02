---
title: "IDebugApplicationThread110::GetActiveThreadRequestCount | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationThread110::GetActiveThreadRequestCount"
ms.assetid: 025d2072-1d7f-4448-8aa3-38a014313570
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IDebugApplicationThread110::GetActiveThreadRequestCount
PDM의 전환 메커니즘은 현재 처리 중인 스레드에서 스레드 요청을 반환 합니다.  이 번호는 일반적으로 0 또는 1입니다.  그러나 한 스레드에서 호출 처리를 시작 하지만 트리거하는 동기 호출에서 스레드를 또는 그렇지 스레드를 일시 중단 및 다시 처리 하는 들어오는 호출을 허용 경우 더 높은 수 있습니다 \(예를 들어, 트리거 여는 [IRemoteDebugApplicationEvents 인터페이스](../../winscript/reference/iremotedebugapplicationevents-interface.md) 디버거 스레드에서 발생 하는 이벤트\).  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT GetActiveThreadRequestCount([out, annotation("_Out_")] UINT * puiThreadRequests);  
  
```  
  
#### 매개 변수  
 `puiThreadRequests`  
 \[out\] 스레드가 요청 횟수입니다.  
  
## 참고 항목  
 [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)
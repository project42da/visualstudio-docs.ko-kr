---
title: "IDebugApplicationThread110::IsThreadCallable | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IDebugApplicationThread110::IsThreadCallable"
ms.assetid: 2a75a366-801d-47e0-bba3-51aa669e03a7
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IDebugApplicationThread110::IsThreadCallable
이 스레드 PDM의 스레드 전환 Synchronouscallinthread와 같은 메커니즘을 사용 하 여 호출을 처리 하는 상태에서 인지 여부를 확인 합니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT IsThreadCallable([out, annotation("_Out_")] BOOL * pfIsCallable);  
```  
  
#### 매개 변수  
 `pfIsCallable`  
 \[out\] `true` 스레드가 그렇지, 호출할 수 있는 경우 `false`.  
  
## 참고 항목  
 [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)
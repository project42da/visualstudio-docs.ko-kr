---
title: "IDebugApplicationThread110::AsynchronousCallIntoThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 06b3031a-4aec-4a47-afaa-04642a4c4870
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# IDebugApplicationThread110::AsynchronousCallIntoThread
주 스레드에서 비동기 호출을 만듭니다.  
  
> [!IMPORTANT]
>  [IDebugApplicationThread110 인터페이스](../../winscript/reference/idebugapplicationthread110-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT AsynchronousCallInMainThread([in] IDebugThreadCall* pptc, [in] DWORD_PTR dwParam1, [in] DWORD_PTR dwParam2, [in] DWORD_PTR dwParam3);  
  
```  
  
#### 매개 변수  
 `pptc`  
 [IDebugThreadCall 인터페이스](../../winscript/reference/idebugthreadcall-interface.md) 를 호출 하는 개체입니다.  
  
 `dwParam1`  
 호출의 첫 번째 매개 변수입니다.  
  
 `dwParam1`  
 호출의 첫 번째 매개 변수입니다.  
  
 `dwParam2`  
 두 번째 매개 변수를 호출 합니다.  
  
 `dwParam3`  
 세 번째 매개 변수를 호출 합니다.  
  
## 참고 항목  
 [IDebugApplication110 인터페이스](../../winscript/reference/idebugapplication110-interface.md)
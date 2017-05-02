---
title: "IJsDebugProcess::CreateStackWalker 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugProcess.CreateStackWalker
apilocation: jscript9diag.dll
ms.assetid: 9d02e21d-7900-4942-8d17-cd04a2261463
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugProcess::CreateStackWalker 메서드
스택 워커에 대한 팩터리 메서드입니다.  
  
## 구문  
  
```  
HRESULT CreateStackWalker(  
   DWORD threadId,  
   IJsDebugStackWalker **ppStackWalker  
);  
```  
  
#### 매개 변수  
 `threadId`  
 \[in\] 스레드 ID입니다.  
  
 `ppStackWalker`  
 \[out\] 새 스택 워커 개체입니다.  
  
## 반환 값  
  
## 설명  
 E\_JsDEBUG\_UNKNOWN\_THREAD 스레드가 없으면 JavaScript에 반환됩니다.  이 메서드는 대상 프로세스가 중지된 동안에만 호출할 수 있습니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugProcess 인터페이스](../../winscript/reference/ijsdebugprocess-interface.md)
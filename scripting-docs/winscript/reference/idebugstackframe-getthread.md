---
title: "IDebugStackFrame::GetThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugStackFrame.GetThread
apilocation: jscript.dll
helpviewer_keywords: 
  - "IDebugStackFrame::GetThread"
ms.assetid: ece24728-a6b2-4b01-a6f0-0a82b15be39b
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugStackFrame::GetThread
이 스택 프레임과 연결 된 스레드를 반환 합니다.  
  
## 구문  
  
```  
HRESULT GetThread(  
   IDebugApplicationThread**  ppat  
);  
```  
  
#### 매개 변수  
 `ppat`  
 \[out\] 이 스택 프레임과 연결 된 스레드입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 이 스택 프레임과 연결 스레드가이 메서드를 반환 합니다.  
  
## 참고 항목  
 [IDebugStackFrame 인터페이스](../../winscript/reference/idebugstackframe-interface.md)
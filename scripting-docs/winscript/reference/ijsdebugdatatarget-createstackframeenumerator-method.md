---
title: "IJsDebugDataTarget::CreateStackFrameEnumerator 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJsDebugDataTarget.CreateStackFrameEnumerator
apilocation: jscript9diag.dll
ms.assetid: cda172e5-18d0-43c5-81d8-432ab30ee70d
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugDataTarget::CreateStackFrameEnumerator 메서드
스택 프레임에 대한 열거자를 만듭니다.  
  
## 구문  
  
```  
HRESULT CreateStackFrameEnumerator(  
   DWORD threadId,  
   IEnumJsStackFrames **ppEnumerator  
);  
```  
  
#### 매개 변수  
 `threadId`  
 \[in\] 대상 프로세스에서 실행되는 스레드입니다.  
  
 `ppEnumerator`  
 \[out\] 스택 프레임에 대한 열거자입니다.  
  
## 반환 값  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugDataTarget 인터페이스](../../winscript/reference/ijsdebugdatatarget-interface.md)
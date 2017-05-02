---
title: "IDebugApplication::RemoveStackFrameSniffer | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.RemoveStackFrameSniffer
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::RemoveStackFrameSniffer"
ms.assetid: 00304b88-e435-4b87-a331-44e7492eb32d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::RemoveStackFrameSniffer
이 응용 프로그램에서 스택 프레임 표시기 공급자를 제거합니다.  
  
## 구문  
  
```  
HRESULT RemoveStackFrameSniffer(  
   DWORD  dwCookie  
);  
```  
  
#### 매개 변수  
 `dwCookie`  
 \[in\] 반환 되는 쿠키는 `AddStackFrameSniffer` 스택 프레임 표시기 공급자를 추가할 때 메서드.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 `RemoveStackFrameSniffer` 메서드는이 응용 프로그램에서 스택 프레임 표시기 공급자를 제거 합니다.  
  
## 참고 항목  
 [IDebugApplication::AddStackFrameSniffer](../../winscript/reference/idebugapplication-addstackframesniffer.md)   
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugStackFrameSniffer 인터페이스](../../winscript/reference/idebugstackframesniffer-interface.md)
---
title: "IJsDebugBreakPoint::Disable 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IJSDebugBreakPoint.Disable
apilocation: jscript9diag.dll
ms.assetid: f6f2889c-c001-4ee5-8e3f-4f36235e4fad
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IJsDebugBreakPoint::Disable 메서드
중단점을 사용하지 않도록 설정합니다.  
  
## 구문  
  
```  
HRESULT Disable(void);  
```  
  
## 반환 값  
  
## 설명  
 삭제된 중단점에서 E\_UNEXPECTED를 반환합니다.  이미 비활성되어 있는 중단점에서 호출된 S\_FALSE를 반환합니다.  
  
## 요구 사항  
 **헤더:** jscript9diag.h  
  
## 참고 항목  
 [IJsDebugBreakPoint 인터페이스](../../winscript/reference/ijsdebugbreakpoint-interface.md)
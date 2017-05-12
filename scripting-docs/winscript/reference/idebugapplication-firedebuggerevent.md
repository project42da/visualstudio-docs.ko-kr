---
title: "IDebugApplication::FireDebuggerEvent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.FireDebuggerEvent
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::FireDebuggerEvent"
ms.assetid: fd1f602e-fc15-4158-a6e7-497ff5b4a509
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::FireDebuggerEvent
일반 이벤트는 디버거를 발생 시키는 `IApplicationDebugger` 인터페이스.  
  
## 구문  
  
```  
HRESULT FireDebuggerEvent(  
   REFGUID    riid,  
   IUnknown*  punk  
);  
```  
  
#### 매개 변수  
 `riid`  
 \[in\] 개체의 GUID입니다.  
  
 `punk`  
 \[in\] 디버거에 전달 되는 이벤트 개체입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|이 메서드는 현재 구현 되지 않았습니다.|  
  
## 설명  
 GUID의 의미와 `IUnknown` 완전히 응용 프로그램\/디버거 정의 됩니다.  
  
 이 메서드는 디버거 모델의 사용자 지정 확장에 대 한 있습니다. 현재 구현 되지 않았습니다.  
  
 이 메서드로 인해 `IApplicationDebugger::onDebuggerEvent` 호출할 수 있습니다.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IApplicationDebugger::onDebuggerEvent](../../winscript/reference/iapplicationdebugger-ondebuggerevent.md)
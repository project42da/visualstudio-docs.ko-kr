---
title: "IApplicationDebugger::onDebuggerEvent | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IApplicationDebugger.onDebuggerEvent
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IApplicationDebugger::onDebuggerEvent"
ms.assetid: 82a5faaa-1222-4bf1-8569-10439dbdf16d
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IApplicationDebugger::onDebuggerEvent
사용자 지정 응용 프로그램 이벤트를 처리합니다.  
  
## 구문  
  
```  
HRESULT onDebuggerEvent(  
   REFIID     riid,  
   IUnknown*  punk  
);  
```  
  
#### 매개 변수  
 `riid`  
 \[in\] 개체의 인터페이스 식별자입니다.  
  
 `punk`  
 \[in\] 이벤트 개체를 정의 하는 인터페이스를 구현 하는 `riid`.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_NOTIMPL`|이 메서드는 현재 구현 되지 않았습니다.|  
  
## 설명  
 의미는 `IUnknown` 는 완전히 정의 된 응용 프로그램\/디버거.  
  
 이 메서드는 디버거 모델의 사용자 지정 확장에 대 한 있습니다. 현재 구현 되지 않았습니다.  
  
 이 메서드가 호출 되 `IDebugApplication::FireDebuggerEvent` 라고 합니다.  
  
## 참고 항목  
 [IApplicationDebugger 인터페이스](../../winscript/reference/iapplicationdebugger-interface.md)   
 [IDebugApplication::FireDebuggerEvent](../../winscript/reference/idebugapplication-firedebuggerevent.md)
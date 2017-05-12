---
title: "IDebugApplication::SynchronousCallInDebuggerThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplication.SynchronousCallInDebuggerThread
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplication::SynchronousCallInDebuggerThread"
ms.assetid: 9daa1722-f25a-4691-aefc-fd28672fb883
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplication::SynchronousCallInDebuggerThread
호출자가 코드에 디버거 스레드가 실행 하는 메커니즘을 제공 합니다.  
  
## 구문  
  
```  
HRESULT SynchronousCallInDebuggerThread(  
   IDebugThreadCall*  pptc,  
   DWORD_PTR          dwParam1,  
   DWORD_PTR          dwParam2,  
   DWORD_PTR          dwParam3  
);  
```  
  
#### 매개 변수  
 `pptc`  
 \[in\] 호출 하는 개체입니다.  
  
 `dwParam1`  
 \[in\] 첫 번째 매개 변수를 전달 하는 `IDebugThreadCall::ThreadCallHandler` 메서드.  
  
 `dwParam2`  
 \[in\] 두 번째 매개 변수를 전달 하는 `IDebugThreadCall::ThreadCallHandler` 메서드.  
  
 `dwParam3`  
 \[in\] 세 번째 매개 변수를 전달 하는 `IDebugThreadCall::ThreadCallHandler` 메서드.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 일반적으로 언어 엔진 및 호스트 위에 해당 단일 스레드 구현 개체 자유 스레드된 구현에이 메서드를 사용.  
  
## 참고 항목  
 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md)   
 [IDebugThreadCall 인터페이스](../../winscript/reference/idebugthreadcall-interface.md)
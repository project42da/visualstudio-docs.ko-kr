---
title: "IRemoteDebugApplication::ConnectDebugger | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.ConnectDebugger
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::ConnectDebugger"
ms.assetid: ded94101-7efe-466f-aa70-b3e30a38c4d8
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::ConnectDebugger
이 응용 프로그램에 디버거를 연결합니다.  
  
## 구문  
  
```  
HRESULT ConnectDebugger(  
   IApplicationDebugger*  pad  
);  
```  
  
#### 매개 변수  
 `pad`  
 \[in\] 이 응용 프로그램에 연결할 디버거입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
|`E_FAIL`|디버거는이 응용 프로그램에 이미 연결 되어 있습니다.|  
  
## 설명  
 응용 프로그램 연결 한 번에 하나의 디버거를 가질 수 있습니다.  디버거가 이미 연결 되어 있는 경우이 메서드가 실패 합니다.  
  
## 참고 항목  
 [IRemoteDebugApplication::GetDebugger](../../winscript/reference/iremotedebugapplication-getdebugger.md)   
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)
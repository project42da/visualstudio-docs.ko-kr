---
title: "IRemoteDebugApplication::QueryAlive | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.QueryAlive
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::QueryAlive"
ms.assetid: 08e49d3b-6fb3-4438-960e-f05395ba9b17
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::QueryAlive
응용 프로그램 응답 인지 여부를 나타냅니다.  
  
## 구문  
  
```  
HRESULT QueryAlive();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 응용 프로그램이 응답 하지 경우이 메서드를 나타냅니다.  이 메서드의 구현은 항상 반환 `S_OK`.  
  
 응용 프로그램 프로세스가 예기치 않게 종료 되 면 COM 마샬링 프록시가 메서드 호출에 대해 오류가 반환 합니다.  
  
## 참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)
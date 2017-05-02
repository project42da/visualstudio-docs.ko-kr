---
title: "IRemoteDebugApplication::EnumThreads | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IRemoteDebugApplication.EnumThreads
apilocation: pdm.dll
helpviewer_keywords: 
  - "IRemoteDebugApplication::EnumThreads"
ms.assetid: b4d7294c-1f15-4f7e-bdfd-700e3bf98cea
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IRemoteDebugApplication::EnumThreads
응용 프로그램에 연결 하는 모든 스레드를 열거 합니다.  
  
## 구문  
  
```  
HRESULT EnumThreads(  
   IEnumRemoteDebugApplicationThreads**  pperdat  
);  
```  
  
#### 매개 변수  
 `pperdat`  
 \[out\] 응용 프로그램에 연결 하는 모든 스레드를 나열 하는 열거자입니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 설명  
 응용 프로그램에 연결 된 것으로 알려진 모든 스레드가이 메서드를 열거 합니다.  언제 든 지 새 스레드를 추가할 수 있습니다.  
  
## 참고 항목  
 [IRemoteDebugApplication 인터페이스](../../winscript/reference/iremotedebugapplication-interface.md)
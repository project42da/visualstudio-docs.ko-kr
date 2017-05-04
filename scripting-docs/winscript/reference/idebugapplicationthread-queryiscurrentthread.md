---
title: "IDebugApplicationThread::QueryIsCurrentThread | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDebugApplicationThread.QueryIsCurrentThread
apilocation: pdm.dll
helpviewer_keywords: 
  - "IDebugApplicationThread::QueryIsCurrentThread"
ms.assetid: 1580d3aa-3be8-4779-ac7b-41ab5c9edede
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDebugApplicationThread::QueryIsCurrentThread
이 스레드에서 현재 실행 중인 스레드가 있는지 확인 합니다.  
  
## 구문  
  
```  
HRESULT QueryIsCurrentThread();  
```  
  
#### 매개 변수  
 이 메서드는 매개 변수를 사용하지 않습니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값 포함 되지만, 다음 테이블에 제한 되지는지 않습니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공 하 고 현재 실행 중인 스레드입니다.|  
|`S_FALSE`|현재 실행 중인 스레드입니다.|  
  
## 설명  
 이 메서드는이 스레드의 현재 실행 중인 스레드가 있는지 확인 합니다.  
  
## 참고 항목  
 [IDebugApplicationThread 인터페이스](../../winscript/reference/idebugapplicationthread-interface.md)
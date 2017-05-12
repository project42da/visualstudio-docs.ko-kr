---
title: "IActiveScriptTraceInfo::StartScriptTracing 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 90fac5ed-ce15-49b7-a6f1-605ede6f34e2
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IActiveScriptTraceInfo::StartScriptTracing 메서드
스크립트 추적을 시작합니다.  
  
## 구문  
  
```  
HRESULT StartScriptTracing(   
    [in] IActiveScriptSiteTraceInfo * pSiteTraceInfo,   
    [in] GUID guidContextID   
);  
  
```  
  
#### 매개 변수  
 `pSiteTraceInfo`  
 Iactivescriptsitetraceinfo는 호스트에 대 한 포인터입니다.  
  
 `guidContextId`  
 컨텍스트의 GUID입니다.  
  
## 반환 값  
 이 메서드의 가능한 반환 값은 다음과 같습니다.  
  
1.  S\_OK: 성공.  
  
2.  E\_POINTER: `pSiteTraceInfo` 은 NULL 포인터입니다.  
  
3.  E\_NOTIMPL: 구현 되지 않았습니다.
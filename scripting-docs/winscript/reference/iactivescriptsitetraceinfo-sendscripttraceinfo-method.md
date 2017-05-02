---
title: "IActiveScriptSiteTraceInfo::SendScriptTraceInfo 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0419e4c5-eb7c-45a3-b6dc-1a5e157d95f9
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IActiveScriptSiteTraceInfo::SendScriptTraceInfo 메서드
이벤트 유형, 컨텍스트 및 스크립트 문을 포함 하는 추적 정보를 보냅니다.  
  
## 구문  
  
```  
HRESULT SendScriptTraceInfo(   
    [in] SCRIPTTRACEINFO stiEventType,   
    [in] GUID guidContextID,   
    [in] DWORD dwScriptContextCookie,   
    [in] LONG lScriptStatementStart,   
    [in] LONG lScriptStatementEnd,   
    [in] DWORD64 dwReserved   
);   
```  
  
#### 매개 변수  
 `stiEventType`  
 이벤트 형식입니다.  
  
 `guidContextId`  
 컨텍스트의 GUID입니다.  
  
 `dwScriptContextCookie`  
 컨텍스트 쿠키입니다.  
  
 `lScriptStatementStart`  
 스크립트 문의의 시작 위치입니다.  
  
 `lScriptStatementEnd`  
 스크립트 문의 끝의 위치입니다.  
  
 `dwReserved`  
 예약되었습니다.
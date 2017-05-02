---
title: "SCRIPTTRACEINFO 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: cb8a4767-8c8e-4fa0-a735-038767a8c500
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# SCRIPTTRACEINFO 열거형
추적 되는 스크립트 이벤트를 나타냅니다.  사용 되는 [IActiveScriptSiteTraceInfo::SendScriptTraceInfo 메서드](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md).  
  
## 구문  
  
```  
typedef enum tagSCRIPTTRACEINFO {    
    SCRIPTTRACEINFO_SCRIPTSTART = 0,    
    SCRIPTTRACEINFO_SCRIPTEND   = 1,    
    SCRIPTTRACEINFO_COMCALLSTART    = 2,    
    SCRIPTTRACEINFO_COMCALLEND  = 3,    
    SCRIPTTRACEINFO_CREATEOBJSTART  = 4,    
    SCRIPTTRACEINFO_CREATEOBJEND    = 5,    
    SCRIPTTRACEINFO_GETOBJSTART = 6,    
    SCRIPTTRACEINFO_GETOBJEND   = 7,    
} SCRIPTTRACEINFO ;  
```  
  
## 열거형 값  
  
|||  
|-|-|  
|SCRIPTTRACEINFO\_SCRIPTSTART|스크립트를 시작 합니다.|  
|SCRIPTTRACEINFO\_SCRIPTEND|종료 스크립트입니다.|  
|SCRIPTTRACEINFO\_COMCALLSTART|COM 호출을 시작 합니다.|  
|SCRIPTTRACEINFO\_COMCALLEND|COM 호출의 끝입니다.|  
|SCRIPTTRACEINFO\_CREATEOBJSTART|개체 생성을 시작 합니다.|  
|SCRIPTTRACEINFO\_CREATEOBJEND|개체 만들기 끝입니다.|  
|SCRIPTTRACEINFO\_GETOBJSTART|GetObject 호출을 시작 합니다.|  
|SCRIPTTRACEINFO\_GETOBJEND|GetObject 호출의 끝입니다.|
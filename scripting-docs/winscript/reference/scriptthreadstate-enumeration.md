---
title: "SCRIPTTHREADSTATE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: SCRIPTTHREADSTATE
apilocation: scrobj.dll
helpviewer_keywords: 
  - "SCRIPTTHREADSTATE 열거형"
ms.assetid: 975ec66b-c095-40ac-8ba9-631adb97b589
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# SCRIPTTHREADSTATE 열거형
스크립팅 엔진에는 스레드의 상태를 지정합니다.  이 열거형은 [IActiveScript::GetScriptThreadState](../../winscript/reference/iactivescript-getscriptthreadstate.md) 메서드에서 사용됩니다.  
  
## 구문  
  
```  
typedef enum tagSCRIPTTHREADSTATE {  
    SCRIPTTHREADSTATE_NOTINSCRIPT  = 0,  
    SCRIPTTHREADSTATE_RUNNING      = 1  
} SCRIPTTHREADSTATE;  
```  
  
## 열거형 값  
  
|||  
|-|-|  
|SCRIPTTHREADSTATE\_NOTINSCRIPT|현재 지정 된 스레드는 스크립트 이벤트 처리를 즉시 실행 하는 스크립트 텍스트를 처리 또는 스크립트 매크로 실행.|  
|SCRIPTTHREADSTATE\_RUNNING|적극적으로 지정 된 스레드는 스크립트 이벤트 처리를 즉시 실행 하는 스크립트 텍스트를 처리 또는 스크립트 매크로 실행.|  
  
## 참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)
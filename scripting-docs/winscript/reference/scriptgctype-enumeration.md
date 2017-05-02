---
title: "SCRIPTGCTYPE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: f289cc7d-2a69-4720-bee0-ea27d054f308
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# SCRIPTGCTYPE 열거형
가비지 수집을 수행 하려면 유형을 지정 합니다.  [IActiveScriptGarbageCollector::CollectGarbage](../../winscript/reference/iactivescriptgarbagecollector-collectgarbage.md) 메서드에 사용됩니다.  
  
## 구문  
  
```cpp  
typedef enum tagSCRIPTGCTYPE {  
    SCRIPTGCTYPE_NORMAL           = 0,  
    SCRIPTGCTYPE_EXHAUSTIVE       = 1,  
} SCRIPTGCTYPE;  
  
```  
  
## 열거형 값  
  
|||  
|-|-|  
|SCRIPTGCTYPE\_NORMAL|기본 가비지 수집을 수행 합니다.  정수 값은 0입니다.|  
|SCRIPTGCTYPE\_EXHAUSTIVE|철저 한 가비지 수집을 수행 합니다.  정수 값은 1입니다.|  
  
## 참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)
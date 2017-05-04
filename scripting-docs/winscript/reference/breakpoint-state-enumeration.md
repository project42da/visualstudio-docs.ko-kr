---
title: "BREAKPOINT_STATE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: BREAKPOINT_STATE
apilocation: scrobj.dll
helpviewer_keywords: 
  - "BREAKPOINT_STATE 열거형"
ms.assetid: 7adc9341-129a-4948-9669-0906d545fd5c
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# BREAKPOINT_STATE 열거형
중단점의 상태를 나타냅니다.  
  
## 구문  
  
```  
typedef enum tagBREAKPOINT_STATE {  
   BREAKPOINT_DELETED = 0,  
   BREAKPOINT_DISABLED = 1,  
   BREAKPOINT_ENABLED = 2  
} BREAKPOINT_STATE;  
```  
  
## Members  
  
|멤버|설명|  
|--------|--------|  
|BREAKPOINT\_DELETED|중단점을 더 이상 존재를 계속 참조 됩니다.|  
|BREAKPOINT\_DISABLED|중단점은 존재 하지만 사용할 수 없습니다.|  
|BREAKPOINT\_ENABLED|중단점이 활성화 되어 있으며.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
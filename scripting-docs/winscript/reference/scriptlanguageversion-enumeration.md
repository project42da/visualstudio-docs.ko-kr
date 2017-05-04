---
title: "SCRIPTLANGUAGEVERSION 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 58aa904a-e3ed-41c6-82d6-e91c8279a792
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# SCRIPTLANGUAGEVERSION 열거형
버전 스크립팅 가능한을 지정 합니다.  
  
## 구문  
  
```cpp  
typedef enum tagSCRIPTLANGUAGEVERSION  
{  
    SCRIPTLANGUAGEVERSION_DEFAULT = 0,  
    SCRIPTLANGUAGEVERSION_5_7  = 1,  
    SCRIPTLANGUAGEVERSION_5_8  = 2,  
    SCRIPTLANGUAGEVERSION_MAX  = 255  
} SCRIPTLANGUAGEVERSION ;  
  
```  
  
## 열거형 값  
  
|||  
|-|-|  
|SCRIPTLANGUAGEVERSION\_DEFAULT|기본 버전입니다.  정수 값은 0입니다.|  
|SCRIPTLANGUAGEVERSION\_5\_7|Windows 스크립트 5.7 버전입니다.  정수 값은 1입니다.|  
|SCRIPTLANGUAGEVERSION\_5\_8|Windows 스크립트 5.8 버전입니다.  정수 값은 2입니다.|  
|SCRIPTLANGUAGEVERSION\_MAX|최대 버전입니다.  정수 값은 255입니다.|  
  
## 참고 항목  
 [액티브 스크립트 상수, 열거형 및 오류 코드](../../winscript/reference/active-script-constants-enumerations-and-error-codes.md)
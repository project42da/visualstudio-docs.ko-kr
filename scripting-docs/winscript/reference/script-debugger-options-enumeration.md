---
title: "SCRIPT_DEBUGGER_OPTIONS 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "SCRIPT_DEBUGGER_OPTIONS 열거형"
ms.assetid: aef41ec0-6f65-48e8-a69e-44b4e4fb929f
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# SCRIPT_DEBUGGER_OPTIONS 열거형
옵션 및 연결 된 디버거를 적용 하는 기능 집합을 나타냅니다.  사용 [IDebugApplicationNode100::GetExcludedDocuments](../../winscript/reference/idebugapplicationnode100-getexcludeddocuments.md) 및[IDebugApplicationNode100::SetFilterForEventSink](../../winscript/reference/idebugapplicationnode100-setfilterforeventsink.md)  
  
> [!IMPORTANT]
>  이러한 상수는 PDM v 10.0이 고 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```  
typedef SCRIPT_DEBUGGER_OPTIONS  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|SDO\_NONE|0x00000000|옵션이 설정되지 않습니다.|  
|SDO\_ENABLE\_FIRST\_CHANCE\_EXCEPTIONS|0x00000001|스크립트 런타임 예외가 throw 될 때 BREAKREASON\_ERROR 이벤트를 발생 시켜야 합니다 것을 나타냅니다.  이 옵션은 디버거를 통해 설정 또는 사용자 코드를 통해 설정할 수 있습니다 `Debug.enableFirstChanceExceptions(<true&#124;false>)`.|  
|SDO\_ENABLE\_WEB\_WORKER\_SUPPORT|0x00000002|연결 된 디버거가 웹 근로자를 지원함을 나타냅니다.|  
  
## 참고 항목  
 [액티브 스크립트 디버거 상수, 열거형 및 구조체](../../winscript/reference/active-script-debugger-constants-enumerations-and-structures.md)
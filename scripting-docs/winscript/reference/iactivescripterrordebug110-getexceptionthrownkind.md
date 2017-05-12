---
title: "IActiveScriptErrorDebug110::GetExceptionThrownKind | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptErrorDebug110::QueryIsFirstChance"
ms.assetid: ecc16e54-93e4-4322-ae13-afa7cd860032
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# IActiveScriptErrorDebug110::GetExceptionThrownKind
Throw된 예외의 종류를 나타내는 값을 반환합니다.  
  
> [!IMPORTANT]
>  [IActiveScriptErrorDebug110 인터페이스](../../winscript/reference/iactivescripterrordebug110-interface.md)은 PDM 버전 11.0 이상에 의해 구현됩니다.  activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```  
HRESULT GetExceptionThrownKind(  
   SCRIPT_ERROR_DEBUG_EXCEPTION_THROWN_KIND*  pExceptionKind  
);  
```  
  
#### 매개 변수  
 `pExceptionKind`  
 \[out\] Throw되는 예외의 종류로서\(예: 첫 번째 발생 가능한 예외 또는 처리되지 않은 예외\), [SCRIPT\_ERROR\_DEBUG\_EXCEPTION\_THROWN\_KIND 열거형](../../winscript/reference/script-error-debug-exception-thrown-kind-enumeration.md) 열거형 값으로 표현됩니다.  
  
## 반환 값  
 이 메서드는 `HRESULT`를 반환합니다.  가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-------|--------|  
|`S_OK`|메서드가 성공했으며|  
  
## 참고 항목  
 [IActiveScriptErrorDebug110 인터페이스](../../winscript/reference/iactivescripterrordebug110-interface.md)
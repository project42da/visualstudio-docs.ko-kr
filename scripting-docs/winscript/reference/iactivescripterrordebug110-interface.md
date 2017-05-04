---
title: "IActiveScriptErrorDebug110 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptErrorDebug110 인터페이스"
ms.assetid: 5c1a4993-4cad-4ccf-89c2-53abfddfe1f2
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScriptErrorDebug110 인터페이스
[IActiveScriptDebug 인터페이스](../../winscript/reference/iactivescriptdebug-interface.md)에 기능을 추가합니다.  이 인터페이스는 BREAKREASON\_ERROR 이벤트가 발생한 이유를 확인하기 위해 JavaScript 엔진에 의해 구현됩니다.  
  
> [!IMPORTANT]
>  이 인터페이스는 PDM v11.0 이상에 의해 구현됩니다.  activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IActiveScriptErrorDebug110` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptErrorDebug110::GetExceptionThrownKind](../../winscript/reference/iactivescripterrordebug110-getexceptionthrownkind.md)|Throw된 예외에 대한 예외 종류를 반환합니다.|
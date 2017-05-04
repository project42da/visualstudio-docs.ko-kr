---
title: "IActiveScriptWinRTErrorDebug 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptWinRTErrorDebug 인터페이스"
ms.assetid: 58b45096-633f-479f-95c4-8eae7376d3a1
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IActiveScriptWinRTErrorDebug 인터페이스
확장된 Windows 런타임 오류 정보를 제공 하는 JavaScript 엔진에 의해 구현 된 [BREAKREASON 열거형](../../winscript/reference/breakreason-enumeration.md) 이벤트.  하는 Queryinterface를 수행할 수 있습니다는 [IActiveScriptError](../../winscript/reference/iactivescripterror.md) 개체입니다.  
  
> [!IMPORTANT]
>  V11.0 PDM 및 큰이 인터페이스를 구현 합니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 `IActiveScriptWinRTErrorDebug` 인터페이스는 다음 메서드를 노출합니다.  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptWinRTErrorDebug::GetCapabilitySid](../../winscript/reference/iactivescriptwinrterrordebug-getcapabilitysid.md)|사용 가능한 경우 Windows 런타임 오류에 대 한 SID 기능을 반환 합니다.|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorReference](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorreference.md)|반환 Windows 런타임 오류 참조 문자열을 사용할 수 있는 경우 제한.|  
|[IActiveScriptWinRTErrorDebug::GetRestrictedErrorString](../../winscript/reference/iactivescriptwinrterrordebug-getrestrictederrorstring.md)|반환 Windows 런타임 오류 문자열을 사용할 수 있는 경우 제한.|
---
title: "액티브 스크립트 상수, 열거형 및 오류 코드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: aab24471-5817-45c0-be07-ffe4648923ed
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# 액티브 스크립트 상수, 열거형 및 오류 코드
열거형과 Windows 스크립트 엔진에서 사용 하는 오류 코드 설명 합니다.  
  
## 상수  
  
|상수|설명|  
|--------|--------|  
|[SCRIPTTHREADID 상수](../../winscript/reference/scriptthreadid-constants.md)|스레드 유형을 지정합니다.|  
  
## 속성  
  
|Property|설명|  
|--------------|--------|  
|[SCRIPTPROP\_HOSTKEEPALIVE 속성](../../winscript/reference/scriptprop-hostkeepalive-property.md)|스크립팅 엔진이 해결 되지 않은 참조가 있는 경우 완벽 하 게 작동 유지 해야 하는지 여부를 지정 하는 데 사용 합니다.|  
  
## 열거형  
  
|열거형|설명|  
|---------|--------|  
|[SCRIPTGCTYPE 열거형](../../winscript/reference/scriptgctype-enumeration.md)|가비지 수집을 수행 하려면 유형을 지정 합니다.|  
|[SCRIPTLANGUAGEVERSION 열거형](../../winscript/reference/scriptlanguageversion-enumeration.md)|버전 스크립팅 가능한을 지정 합니다.|  
|[SCRIPTSTATE 열거형](../../winscript/reference/scriptstate-enumeration.md)|스크립팅 엔진의 상태를 지정합니다.|  
|||  
|[SCRIPTTHREADSTATE 열거형](../../winscript/reference/scriptthreadstate-enumeration.md)|스크립팅 엔진에는 스레드의 상태를 지정합니다.|  
|[SCRIPTTRACEINFO 열거형](../../winscript/reference/scripttraceinfo-enumeration.md)|추적 되는 스크립트 이벤트를 나타냅니다.  사용 되는 [IActiveScriptSiteTraceInfo::SendScriptTraceInfo 메서드](../../winscript/reference/iactivescriptsitetraceinfo-sendscripttraceinfo-method.md).|  
|[SCRIPTUICHANDLING 열거형](../../winscript/reference/scriptuichandling-enumeration.md)|UI 컨트롤을 처리 하는 방식을 나타냅니다.|  
|[SCRIPTUICITEM 열거형](../../winscript/reference/scriptuicitem-enumeration.md)|UI 항목 유형을 나타냅니다.  사용 되는 [IActiveScriptSiteUIControl::GetUIBehavior 메서드](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md).|  
  
## 오류 코드  
  
|오류 코드|설명|  
|-----------|--------|  
|[SCRIPT\_E\_PROPAGATE 오류 코드](../../winscript/reference/script-e-propagate-error-code.md)|스크립트 오류는 다른 스레드를 호출자에 게 전파 됩니다.|  
|[SCRIPT\_E\_RECORDED 오류 코드](../../winscript/reference/script-e-recorded-error-code.md)|스크립트 엔진에서 호스트 사이의 오류가 전달 되었습니다.|  
|[SCRIPT\_E\_REPORTED 오류 코드](../../winscript/reference/script-e-reported-error-code.md)|스크립트 엔진 호스트 처리 되지 않은 예외가 발생 했습니다.|  
  
## 참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)
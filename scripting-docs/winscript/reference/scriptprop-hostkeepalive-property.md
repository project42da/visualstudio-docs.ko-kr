---
title: "SCRIPTPROP_HOSTKEEPALIVE 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: bfa199f2-28ba-4320-bc0f-2320fad018bd
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# SCRIPTPROP_HOSTKEEPALIVE 속성
스크립팅 엔진 해결 되지 않은 참조가 경우에 완벽 하 게 작동 유지 해야 하는지 여부를 지정 하는 데 사용 합니다.  
  
 사용 [IActiveScriptProperty::SetProperty](../../winscript/reference/iactivescriptproperty-setproperty.md) 이 속성을 설정 `true`.  이 속성이 설정 된 경우 `true`, 스크립팅 엔진 스크립팅 엔진 또는 하나 이상의 해결 되지 않은 참조 한 대로 완벽 하 게 작동 유지 되는 `IDispatch` 스크립팅 엔진을 사용 하 여 생성 하는 JavaScript 개체에 대 한 포인터입니다.  이 속성이 설정 되 면 `true`를 명시적으로 닫거나 스크립트 엔진을 사용 하 여 다시 설정 해야는 [IActiveScript::Close](../../winscript/reference/iactivescript-close.md) 또는 [IActiveScript::SetScriptState](../../winscript/reference/iactivescript-setscriptstate.md) 메서드.  스크립트 엔진이 스크립트 개체에 대 한 마지막 참조를 해제 종료 됩니다.  
  
## 구문  
  
```  
#define SCRIPTPROP_HOSTKEEPALIVE 0x70000004  
```  
  
## 요구 사항  
 버전을 함께 설치 하는 activscp.idl에만이 속성을 표시 [!INCLUDE[win8](../../javascript/includes/win8-md.md)], Internet Explorer 8 대해 KB 2707082와 [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)], 또는 Internet Explorer 9 대 한 KB 2722913 [!INCLUDE[win7](../../winscript/reference/includes/win7-md.md)] 또는 [!INCLUDE[vista_first](../../winscript/reference/includes/vista-first-md.md)].
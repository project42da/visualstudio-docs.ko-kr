---
title: "IActiveScriptProperty::GetProperty | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProperty.GetProperty
apilocation: scrobj.dll
helpviewer_keywords: 
  - "GetProperty 메서드, IActiveScriptProperty 인터페이스"
ms.assetid: a43383db-b148-4d76-83bd-4f0e899b7cb1
caps.latest.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 24
---
# IActiveScriptProperty::GetProperty
매개 변수에 의해 지정 된 속성을 가져옵니다.  
  
## 구문  
  
```  
HRESULT GetProperty(  
// The property value:  
    uint dwProperty,    
// Not used:  
    IntPtr pvarIndex,    
// The value of the property:   
    out object pvarValue,    
);  
```  
  
#### 매개 변수  
 `dwProperty`  
 가져올 속성 값입니다.  
  
 `pvarIndex`  
 사용되지 않습니다.  
  
 `pvarValue`  
 속성의 값입니다.  
  
 허용 되는 값 `dwProperty` 는 다음 표에 설명 되어 있습니다.  
  
|상수|값|의미|  
|--------|-------|--------|  
|SCRIPTPROP\_INTEGERMODE|0x00003000|스크립팅 엔진 부동 소수점 모드 대신 정수 모드 구분 됩니다.|  
|SCRIPTPROP\_STRINGCOMPAREINSTANCE|0x00003001|문자열 비교 함수를 스크립팅 엔진 교체가 있습니다.|  
|SCRIPTPROP\_ABBREVIATE\_GLOBALNAME\_RESOLUTION|0x70000002|다른 스크립팅 엔진이 전역 개체를 참가할 수 있는 스크립팅 엔진을 알립니다.|  
|SCRIPTPROP\_INVOKEVERSIONING|0x00004000|군대는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립트 언어 기능을 지원 합니다를 선택 합니다.  기본 집합을 지 원하는 언어 기능을 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진의 버전 5.7에서 나타나는 언어 기능 집합에 해당 하는 것은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
  
## 설명  
 호스트 SCRIPTPROP\_ABBREVIATE\_GLOBALNAME\_RESOLUTION 속성 다른 스크립팅 엔진이 전역 개체를 참가할 수 있는 스크립팅 엔진에 알리기 위해 사용할 수 있습니다.  예를 들어, Internet Explorer 알려줄 수는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 만 렌더링 되는 페이지를 포함 하는 엔진 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립트.  따라서만 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 엔진 전역 개체 창에 새 속성을 추가할 수 및 Visual Basic Scripting Edition \(VBScript\) 엔진이 동일한 작업을 수행할 수 없습니다.  엔진은이 플래그를 무시 하거나 전역 개체에 추가 된 새 구성원의 관리를 최적화할 수 있습니다.  
  
 호스트 언어 기능 집합을 선택 하려면 SCRIPTPROP\_INVOKEVERSIONING 속성을 사용할 수 때 지원 되는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진이 시작 되었습니다.  1 \(SCRIPTLANGUAGEVERSION\_5\_7\)로이 속성을 설정 하면 사용할 수 있는 언어 기능 버전 5.7에 나타나는 것과 동일 되는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진.  2 \(SCRIPTLANGUAGEVERSION\_5\_8\)로 설정 된 경우 사용할 수 있는 언어 기능 버전 5.7에서 5.8 버전에서 추가 된 기능 외에도 처음입니다.  기본적으로이 속성 호스트 다른 기본 동작을 지원 하지 않는 한, 5.7 버전에서 나타났던 언어 기능 집합에 해당 하는입니다 \(SCRIPTLANGUAGEVERSION\_DEFAULT\)를 0으로 설정 됩니다.  예를 들어, Internet Explorer 8 선택할에 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 5.8 버전에서 지원 되는 언어 기능 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] "Internet Explorer 8 표준" 모드의 문서 모드를 Internet Explorer 8 때 기본적으로 스크립트 엔진.  
  
## 참고 항목  
 [문서 호환성 정의](http://msdn.microsoft.com/library/cc288325)   
 [IActiveScriptProperty](../../winscript/reference/iactivescriptproperty.md)   
 [버전 정보](../../javascript/reference/javascript-version-information.md)
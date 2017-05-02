---
title: "IActiveScriptProperty::SetProperty | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptProperty.SetProperty
apilocation: scrobj.dll
helpviewer_keywords: 
  - "SetProperty 메서드, IActiveScriptProperty 인터페이스"
ms.assetid: 0ba429c5-04a3-4505-bc5f-69c505dfca91
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# IActiveScriptProperty::SetProperty
매개 변수에 의해 지정 된 속성을 설정 합니다.  
  
## 구문  
  
```  
HRESULT SetProperty(  
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
 설정할 속성 값입니다.  
  
 `pvarIndex`  
 사용되지 않습니다.  
  
 `pvarValue`  
 속성의 값입니다.  
  
 허용 되는 값 `dwProperty` 는 다음 표에 설명 되어 있습니다.  
  
|상수|값|의미|  
|--------|-------|--------|  
|SCRIPTPROP\_INTEGERMODE|0x00003000|스크립팅 엔진 부동 소수점 모드 대신 정수 모드 구분 됩니다.  기본값은 `False`입니다.|  
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
 정수 나눗셈을 사용 하거나 호출 `SetProperty` 및 변환 된 `Boolean` 에 `Object`.  기본적으로 속성 값인 `False`.  설정는 경우 `True`, 나누기 작업 정수만 반환 됩니다.  
  
 호출을 사용 하거나 사용자 지정 하는 문자열 비교를 사용 하지 않도록 설정 `SetProperty` 에 전달 된 `Object` 값.  전달 된 개체의 인터페이스를 구현 해야 [IActiveScriptStringCompare 인터페이스](../../winscript/reference/iactivescriptstringcompare-interface.md).  [StrComp](../../winscript/reference/iactivescriptstringcompare-strcomp.md) 메서드는 [IActiveScriptStringCompare 인터페이스](../../winscript/reference/iactivescriptstringcompare-interface.md) 인터페이스는 문자열 비교 함수를 실행할 때마다 호출 됩니다.  
  
 때 지원 되지 않는 언어 기능을 선택 하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진을 초기화 하 고 호출 `SetProperty` 및 SCRIPTPROP\_INVOKEVERSIONING를 사용 하려면 설정의 언어 기능에 해당 값을 전달 합니다.  1 \(SCRIPTLANGUAGEVERSION\_5\_7\)로이 속성을 설정 하면 사용할 수 있는 언어 기능 버전 5.7에 나타나는 것과 동일 되는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진.  2 \(SCRIPTLANGUAGEVERSION\_5\_8\)로 설정 된 경우 사용할 수 있는 언어 기능 버전 5.7에서 5.8 버전에서 추가 된 새 기능 외에도 처음입니다.  기본적으로이 속성 호스트 다른 기본 동작을 지원 하지 않는 한, 5.7 버전에서 나타났던 언어 기능 집합에 해당 하는입니다 \(SCRIPTLANGUAGEVERSION\_DEFAULT\)를 0으로 설정 됩니다.  예를 들어, Internet Explorer 8 선택할에 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 5.8 버전에서 지원 되는 언어 기능 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Internet Explorer 8 대 한 기본 문서 모드 "Internet Explorer 8 표준" 모드 이면 기본적으로 스크립트 엔진.  Internet Explorer 8 Internet Explorer 7 표준 모드로 문서 또는 불확정 모드 전환 다시 설정 하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진 버전 5.7에서 있던 언어 기능 들만을 지원 하기 위해 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진.  
  
> [!NOTE]
>  SCRIPTPROP\_INVOKEVERSIONING 경우에만 설정 해야는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진을 초기화 중입니다.  
  
## 예제  
 다음 예제에서는 정수 나누기를 사용 하는 스크립팅 엔진을 강제 하는 방법 및 비교 함수의 오버 로드를 허용 하는 방법을 보여 줍니다.  
  
```csharp  
BMLScriptEngine bmlScriptEngine = new BMLScriptEngine();  
IActiveScriptProperty scriptProperties = bmlScriptEngine as   
    IActiveScriptProperty;  
  
// Force the scripting engine to use integer division.  
Boolean enableIntegerDivision = true;  
Object vtIntegerDivInstance = (Object)enableIntegerDivision;  
                scriptProperties.SetProperty(SCRIPTPROP_INTEGERDIVISION,   
    System.IntPtr.Zero, ref vtIntegerDivInstance);  
  
// Allow overloading of the compare function.  
BMLScriptStringCompare bmlScriptStringCompareInstance = new   
    BMLScriptStringCompare();  
Object vtStrCmpInstance = (Object)bmlScriptStringCompareInstance;  
scriptProperties.SetProperty(SCRIPTPROP_STRCOMPINST,   
    System.IntPtr.Zero, ref vtStrCmpInstance);  
```  
  
## 참고 항목  
 [문서 호환성 정의](http://msdn.microsoft.com/library/cc288325)   
 [IActiveScriptProperty](../../winscript/reference/iactivescriptproperty.md)   
 [버전 정보](../../javascript/reference/javascript-version-information.md)
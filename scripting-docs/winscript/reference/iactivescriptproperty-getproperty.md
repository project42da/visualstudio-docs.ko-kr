---
title: IActiveScriptProperty::GetProperty | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IActiveScriptProperty.GetProperty
apilocation: scrobj.dll
helpviewer_keywords: GetProperty method, IActiveScriptProperty interface
ms.assetid: a43383db-b148-4d76-83bd-4f0e899b7cb1
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d55fb2d816931a74827d318e13860b3f97f0fd23
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptpropertygetproperty"></a>IActiveScriptProperty::GetProperty
매개 변수에 의해 지정 된 속성을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
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
  
#### <a name="parameters"></a>매개 변수  
 `dwProperty`  
 가져올 속성 값입니다.  
  
 `pvarIndex`  
 사용되지 않습니다.  
  
 `pvarValue`  
 속성 값입니다.  
  
 값에 대 한 허용 `dwProperty` 다음 표에 설명 되어 있습니다.  
  
|상수|값|의미|  
|--------------|-----------|-------------|  
|SCRIPTPROP_INTEGERMODE|0x00003000|스크립팅 엔진에 부동 지점 모드 대신 정수 모드로 나누기를 강제로 수행 합니다.|  
|SCRIPTPROP_STRINGCOMPAREINSTANCE|0x00003001|교체 스크립팅 엔진의 문자열 비교 함수가 있습니다.|  
|SCRIPTPROP_ABBREVIATE_GLOBALNAME_RESOLUTION|0x70000002|전역 개체에서 작업할 수 없는 다른 스크립팅 엔진 존재 하는 스크립팅 엔진을 알립니다.|  
|SCRIPTPROP_INVOKEVERSIONING|0x00004000|강제로 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진의 언어 지원 해야 하는 기능 집합을 선택 합니다. 지 원하는 언어 기능의 기본 집합이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진은 버전 5.7 표시 된 언어 기능 집합에 해당 하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진입니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|------------------|-------------|  
|`S_OK`|명령 실행 성공|  
|`E_INVALIDARG`|인수가 잘못된 경우|  
|`E_UNEXPECTED`|호출이 필요 하지 않습니다 (예를 들어 스크립팅 엔진에 로드 되거나 않은 초기화).|  
  
## <a name="remarks"></a>설명  
 호스트는 SCRIPTPROP_ABBREVIATE_GLOBALNAME_RESOLUTION 속성을 사용 하 여 전역 개체에서 작업할 수 없는 다른 스크립팅 엔진 존재 하는 스크립팅 엔진에 알리는 수 있습니다. 예를 들어 Internet Explorer에 알릴 수 있습니다는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 렌더링 되 고 페이지에만 포함 하는 엔진 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립트입니다. 따라서만 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 엔진 전역 개체 창에 새 속성을 추가할 수 이며 동일한 작업을 수행 하려면 Visual Basic Scripting Edition (VBScript) 엔진이 없습니다. 엔진은이 플래그를 무시할 수 또는 전역 개체에 추가 하는 새 구성원의 관리를 최적화 하는 데 사용할 수 있습니다.  
  
 호스트의 되도록 언어 기능 집합을 선택 하려면 SCRIPTPROP_INVOKEVERSIONING 속성을 사용할 수 실행할 수는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진을 시작할 합니다. 사용 가능한 언어 기능 버전 5.7 표시 된 것과 동일 하 게는이 속성을 1 (SCRIPTLANGUAGEVERSION_5_7)로 설정 하는 경우는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 스크립팅 엔진입니다. 2 (SCRIPTLANGUAGEVERSION_5_8)로 설정 된 경우 사용 가능한 언어 기능은 5.8 버전에 추가 된 기능 외에도 5.7 버전에 표시 되었습니다. 기본적으로이 속성 값은 버전 5.7, 표시 된 언어 기능 집합 호스트는 서로 다른 기본 동작을 지원 하지 않는 한 (SCRIPTLANGUAGEVERSION_DEFAULT) 0으로 설정 됩니다. Internet Explorer 8에 opts 예를 들어,는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 5.8 버전에서 지 원하는 언어 기능 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] Internet Explorer 8에 대 한 문서 모드는 "Internet Explorer 8 표준" 모드 때 기본적으로 스크립팅 엔진입니다.  
  
## <a name="see-also"></a>참고 항목  
 [문서 호환성 정의](http://msdn.microsoft.com/library/cc288325)   
 [IActiveScriptProperty](../../winscript/reference/iactivescriptproperty.md)   
 [버전 정보](../../javascript/reference/javascript-version-information.md)
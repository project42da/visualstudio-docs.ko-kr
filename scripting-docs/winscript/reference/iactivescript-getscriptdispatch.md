---
title: "IActiveScript::GetScriptDispatch | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScript.GetScriptDispatch
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScript_GetScriptDispatch"
ms.assetid: 2092ccd4-1f4c-493a-b5b7-077a70ce95ca
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScript::GetScriptDispatch
검색은 `IDispatch` 인터페이스의 메서드 및 속성을 사용 하 여 현재 실행 중인 스크립트에 관련 된.  
  
## 구문  
  
```  
HRESULT GetScriptDispatch(  
    LPCOLESTR pstrItemName  // address of item name  
    IDispatch **ppdisp      // receives IDispatch pointer  
);  
```  
  
#### 매개 변수  
 `pstrItemName`  
 \[in\] 호출자 관련된 디스패치 개체에 대 한 요구 항목의 이름이 들어 있는 버퍼의 주소입니다.  이 매개 변수가 `NULL`, 디스패치 개체 스크립트에 의해 정의 된 모든 전역 메서드 및 속성을 구성원으로 포함 되어 있습니다.  통해는 `IDispatch` 인터페이스 및 연결 된 `ITypeInfo` 인터페이스를 보거나 스크립트 메서드 호출 고 스크립트 변수를 수정 합니다.  
  
 `ppdisp`  
 \[out\] 수신 스크립트의 전역 메서드 및 속성을 연결 된 개체에 대 한 포인터 변수의 주소입니다.  이러한 개체를 스크립팅 엔진을 지원 하지 않는 경우 `NULL` 이 반환 됩니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`E_UNEXPECTED`|호출이 필요 없습니다 \(예를 들어, 스크립팅 엔진이 아직 로드 초기화 되었거나\).|  
|`S_FALSE`|스크립팅 엔진이 디스패치 개체를 지원 하지 않습니다. `ppdisp` 매개 변수를 NULL로 설정 됩니다.|  
  
## 설명  
 속성 및 메서드를 호출 하 여 추가할 수 있으므로 [IActiveScriptParse](../../winscript/reference/iactivescriptparse.md) 인터페이스의 `IDispatch` 이 메서드에서 반환 하는 인터페이스 새 메서드 및 속성을 지원할 수 동적으로.  마찬가지로 `IDispatch::GetTypeInfo` 메서드 반환 해야 새, 고유한 `ITypeInfo` 인터페이스 메서드와 속성을 추가할 때.  그러나 엔진 언어를 변경 해야 한다는 참고는 `IDispatch` 인터페이스는 방식으로 즉 호환 하나에 이전 `ITypeInfo` 인터페이스를 반환 합니다.  , 예를 들어 Dispid 절대로 재사용할 수 합니다 의미 합니다.  
  
## 참고 항목  
 [IActiveScript](../../winscript/reference/iactivescript.md)
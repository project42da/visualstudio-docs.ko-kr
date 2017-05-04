---
title: "IActiveScriptSite::GetItemInfo | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSite.GetItemInfo
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSite_GetItemInfo"
ms.assetid: f859ed3b-02c1-4924-99f8-5f5bf1bf8405
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSite::GetItemInfo
스크립팅 엔진에 추가한 항목에 대 한 정보를 얻을 수 있는 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.  
  
## 구문  
  
```  
HRESULT GetItemInfo(  
    LPCOLESTR pstrName,     // address of item name  
    DWORD dwReturnMask,     // bit mask for information retrieval  
    IUnknown **ppunkItem,   // address of pointer to item's IUnknown  
    ITypeInfo **ppTypeInfo  // address of pointer to item's ITypeInfo  
);  
```  
  
#### 매개 변수  
 `pstrName`  
 \[in\] 지정 된 항목과 관련 된 이름에 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.  
  
 `dwReturnMask`  
 \[in\] 항목에 대 한 정보를 반환할지를 지정 하는 비트 마스크입니다.  스크립팅 엔진 때문에 최소한의 가능한 정보를 요청 해야 일부 반환 매개 변수 \(예를 들어, `ITypeInfo`\)을 로드 하거나 생성 하는 데 상당한 시간이 걸릴 수 있습니다.  다음 값 조합이 될 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|SCRIPTINFO\_IUNKNOWN|반환 된 `IUnknown` 이 항목에 대 한 인터페이스.|  
|SCRIPTINFO\_ITYPEINFO|반환 된 `ITypeInfo` 이 항목에 대 한 인터페이스.|  
  
 `ppunkItem`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `IUnknown` 지정 된 항목에 연결 된 인터페이스.  스크립팅 엔진에서 사용할 수 있습니다는 `IUnknown::QueryInterface` 구하려면 메서드는 `IDispatch` 항목에 대 한 인터페이스.  이 매개 변수에 NULL을 경우 받은 `dwReturnMask` SCRIPTINFO\_IUNKNOWN 값이 포함 되지 않습니다.  또한 관련 항목 이름의 개체가 없으면 NULL을 받습니다. 이 메커니즘 설정 SCRIPTITEM\_CODEONLY 플래그와 명명 된 항목을 추가할 때 간단한 클래스를 만드는 데 사용 되는 [IActiveScript::AddNamedItem](../../winscript/reference/iactivescript-addnameditem.md) 메서드.  
  
 `ppTypeInfo`  
 \[out\] 에 대 한 포인터를 받는 변수의 주소는 `ITypeInfo` 항목에 연결 하는 인터페이스.  경우이 매개 변수에 NULL을 받은 `dwReturnMask` SCRIPTINFO\_ITYPEINFO 값이 포함 되지 않습니다 또는이 항목에 대 한 형식 정보가 없습니다.  형식 정보를 사용할 수 없는 개체, 이벤트의 소스가 없습니다 바인딩 이름으로 실현 해야 경우는 `IDispatch::GetIDsOfNames` 메서드.  참고는 `ITypeInfo` 검색 인터페이스 개체 여러 인터페이스와 이벤트 인터페이스를 지원 하지 않으므로 coclass 항목 \(TKIND\_COCLASS\)을 설명 합니다.  항목을 지 원하는 경우는 `IProvideMultipleTypeInfo` 인터페이스의 `ITypeInfo` 인터페이스 검색 되는 인덱스 0 `ITypeInfo` 하는 얻을 수를 사용 하 여는 `IProvideMultipleTypeInfo::GetInfoOfIndex` 메서드.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|성공|  
|`E_INVALIDARG`|인수가 잘못된 경우.|  
|`E_POINTER`|잘못 된 포인터를 지정 했습니다.|  
|`TYPE_E_ELEMENTNOTFOUND`|지정 된 이름의 항목을 찾을 수 없습니다.|  
  
## 설명  
 이 메서드는 지정 된 정보만 검색은 `dwReturnMask` 매개 변수입니다. 이렇게 하면 성능이 향상 됩니다.  예를 들어, 경우에 `ITypeInfo` 인터페이스 항목에 대 한 필요 하지 않은, 단순히에 지정 하지 `dwReturnMask`.  
  
## 참고 항목  
 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md)
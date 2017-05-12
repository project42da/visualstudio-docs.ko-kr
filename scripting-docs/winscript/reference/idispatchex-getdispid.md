---
title: "IDispatchEx::GetDispID | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.GetDispID
apilocation: scrobj.dll
helpviewer_keywords: 
  - "GetDispID 메서드"
ms.assetid: a288d63d-b08a-4540-9d9d-0bcd182eff9a
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispatchEx::GetDispID
단일 구성원 이름 후속 호출에 사용 되는 수는 해당 DISPID를 매핑합니다 `IDispatchEx::InvokeEx`.  
  
## 구문  
  
```  
 HRESULT GetDispID(  
   BSTR bstrName,  
   DWORD grfdex,  
   DISPID *pid  
);  
```  
  
#### 매개 변수  
 `bstrName`  
 매핑할 이름에 전달 합니다.  
  
 `grfdex`  
 멤버 식별자를 가져오는 옵션이 결정 됩니다.  이 다음 값 조합이 될 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|fdexNameCaseSensitive|대\/소문자 구분 방식으로 이름 조회를 수행할 수 있는 요청 수입니다.  대\/소문자 구분 조회를 지원 하지 않는 개체에 의해 무시 될 수 있습니다.|  
|fdexNameEnsure|존재 하지 않는 경우 멤버를 만들 수를 요청 합니다.  값으로 새 멤버를 만들어야 `VT_EMPTY`.|  
|fdexNameImplicit|기본 개체를 명시적으로 지정 되지 않은 경우 호출자에 대 한 특정 이름의 멤버 객체를 검색 하 고 있음을 나타냅니다.|  
|fdexNameCaseInsensitive|대\/소문자 이름 조회를 수행할 수 있는 요청 수입니다.  대\/소문자 구분 조회를 지원 하지 않는 개체에 의해 무시 될 수 있습니다.|  
  
 `pid`  
 Dispid가 결과 받는 호출자가 할당 위치에 대 한 포인터입니다.  오류가 발생 하면 `pid` DISPID\_UNKNOWN 포함 되어 있습니다.  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|성공|  
|`E_OUTOFMEMORY`|메모리가 부족합니다.|  
|`DISP_E_UNKNOWNNAME`|이름을 알 수 없습니다.|  
  
## 설명  
 `GetDispID`대신 사용할 수 있는 `GetIDsOfNames` 지정 된 멤버에 대 한 DISPID를 얻을 수 있습니다.  
  
 때문에 `IDispatchEx` 추가 및 멤버에서 Dispid 집합이 삭제 하지 유지 상수는 개체의 수명에 대 한 있습니다.  
  
 사용 되지 않은 `riid` 매개 변수에서 `IDispatch::GetIDsOfNames` 제거 되었습니다.  
  
## 예제  
  
```  
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
  
   // Assign to pdex and bstrName  
   pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid);  
   // Use dispid  
```  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)
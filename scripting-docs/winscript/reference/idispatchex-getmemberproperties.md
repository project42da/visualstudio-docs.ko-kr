---
title: "IDispatchEx::GetMemberProperties | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IDispatchEx.GetMemberProperties
apilocation: scrobj.dll
helpviewer_keywords: 
  - "GetMemberProperties 메서드"
ms.assetid: 20d43209-12e2-472a-9bf3-81eced137b71
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IDispatchEx::GetMemberProperties
구성원의 속성을 검색합니다.  
  
## 구문  
  
```  
HRESULT GetMemberProperties(  
   DISPID id,  
   DWORD grfdexFetch,  
   DWORD *pgrfdex  
);  
```  
  
#### 매개 변수  
 `id`  
 멤버를 식별합니다.  사용 하 여 `GetDispID` 또는 `GetNextDispID` 디스패치 식별자를 얻을 수 있습니다.  
  
 `grfdexFetch`  
 검색 하는 속성을 결정 합니다.  이 아래에 나열 된 값을 조합한 수 `pgrfdex` 및\/또는 다음 값의 조합.  
  
|값|의미|  
|-------|--------|  
|grfdexPropCanAll|FdexPropCanGet, fdexPropCanPut, fdexPropCanPutRef, fdexPropCanCall, fdexPropCanConstruct 및 Fdexpropcansourceevents를 결합합니다.|  
|grfdexPropCannotAll|FdexPropCannotGet, fdexPropCannotPut, fdexPropCannotPutRef, fdexPropCannotCall, fdexPropCannotConstruct 및 Fdexpropcannotsourceevents를 결합합니다.|  
|grfdexPropExtraAll|Fdexpropnosideeffects와 Fdexpropdynamictype을 결합합니다.|  
|grfdexPropAll|GrfdexPropCanAll, grfdexPropCannotAll 및 Grfdexpropextraall를 결합합니다.|  
  
 `pgrfdex`  
 주소는 `DWORD` 는 요청 된 속성을 받습니다.  이 다음 값 조합이 될 수 있습니다.  
  
|값|의미|  
|-------|--------|  
|fdexPropCanGet|DISPATCH\_PROPERTYGET를 사용 하 여 멤버를 가져올 수 있습니다.|  
|fdexPropCannotGet|DISPATCH\_PROPERTYGET를 사용 하 여 멤버를 가져올 수 없습니다.|  
|fdexPropCanPut|DISPATCH\_PROPERTYPUT를 사용 하 여 구성원을 설정할 수 있습니다.|  
|fdexPropCannotPut|DISPATCH\_PROPERTYPUT를 사용 하 여 구성원을 설정할 수 없습니다.|  
|fdexPropCanPutRef|DISPATCH\_PROPERTYPUTREF를 사용 하 여 구성원을 설정할 수 있습니다.|  
|fdexPropCannotPutRef|DISPATCH\_PROPERTYPUTREF를 사용 하 여 구성원을 설정할 수 없습니다.|  
|fdexPropNoSideEffects|멤버는 부작용이 없습니다.  예를 들어, 디버거를 안전 하 게: 가져오기\/설정\/호출 수 디버깅 중인 스크립트의 상태를 변경 하지 않고도이 구성원.|  
|fdexPropDynamicType|구성원은 동적 이며 개체의 수명 동안 변경할 수 있습니다.|  
|fdexPropCanCall|DISPATCH\_METHOD 사용 하는 방법으로 멤버를 호출할 수 있습니다.|  
|fdexPropCannotCall|DISPATCH\_METHOD 사용 하는 방법으로 멤버를 호출할 수 없습니다.|  
|fdexPropCanConstruct|DISPATCH\_CONSTRUCT를 사용 하는 생성자로 멤버를 호출할 수 있습니다.|  
|fdexPropCannotConstruct|멤버는 DISPATCH\_CONSTRUCT을 사용 하는 생성자로 호출할 수 없습니다.|  
|fdexPropCanSourceEvents|구성원 이벤트를 발생 시킬 수 있습니다.|  
|fdexPropCannotSourceEvents|멤버는 이벤트를 발생 수 없습니다.|  
  
## 반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|성공|  
|`DISP_E_UNKNOWNNAME`|이름을 알 수 없습니다.|  
  
## 예제  
  
```  
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
   DWORD dwProps;  
  
   // Assign to pdex and bstrName  
   if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)) &&  
      SUCCEEDED(pdex->GetMemberProperties(dispid, grfdexPropAll, &dwProps)) &&  
         (dwProps & fdexPropCanPut))  
   {  
      // Assign to member  
   }  
```  
  
## 참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)
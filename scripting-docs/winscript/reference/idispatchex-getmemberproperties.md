---
title: IDispatchEx::GetMemberProperties | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDispatchEx.GetMemberProperties
apilocation: scrobj.dll
helpviewer_keywords: GetMemberProperties method
ms.assetid: 20d43209-12e2-472a-9bf3-81eced137b71
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0d216bb7b21c8895337b9925007637c00d0deb37
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchexgetmemberproperties"></a>IDispatchEx::GetMemberProperties
멤버의 속성을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMemberProperties(  
   DISPID id,  
   DWORD grfdexFetch,  
   DWORD *pgrfdex  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 멤버를 식별합니다. 사용 하 여 `GetDispID` 또는 `GetNextDispID` 디스패치 식별자를 가져올 수 있습니다.  
  
 `grfdexFetch`  
 속성 검색을 결정 합니다. 아래 나열 된 값의 조합 수 `pgrfdex` 및/또는 다음 값의 조합 합니다.  
  
|값|의미|  
|-----------|-------------|  
|grfdexPropCanAll|FdexPropCanGet, fdexPropCanPut, fdexPropCanPutRef, fdexPropCanCall, fdexPropCanConstruct 및 fdexPropCanSourceEvents 결합합니다.|  
|grfdexPropCannotAll|FdexPropCannotGet, fdexPropCannotPut, fdexPropCannotPutRef, fdexPropCannotCall, fdexPropCannotConstruct 및 fdexPropCannotSourceEvents 결합합니다.|  
|grfdexPropExtraAll|FdexPropNoSideEffects 및 fdexPropDynamicType 결합합니다.|  
|grfdexPropAll|GrfdexPropCanAll, grfdexPropCannotAll 및 grfdexPropExtraAll 결합합니다.|  
  
 `pgrfdex`  
 주소는 `DWORD` 받는 요청 된 속성입니다. 이 다음 값의 조합 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|fdexPropCanGet|DISPATCH_PROPERTYGET를 사용 하 여 멤버를 가져올 수 있습니다.|  
|fdexPropCannotGet|DISPATCH_PROPERTYGET를 사용 하 여 멤버를 가져올 수 없습니다.|  
|fdexPropCanPut|멤버는 DISPATCH_PROPERTYPUT를 사용 하 여 설정할 수 있습니다.|  
|fdexPropCannotPut|멤버는 DISPATCH_PROPERTYPUT를 사용 하 여 설정할 수 없습니다.|  
|fdexPropCanPutRef|멤버는 DISPATCH_PROPERTYPUTREF를 사용 하 여 설정할 수 있습니다.|  
|fdexPropCannotPutRef|멤버는 DISPATCH_PROPERTYPUTREF를 사용 하 여 설정할 수 없습니다.|  
|fdexPropNoSideEffects|멤버에는 프로그램의 부작용이 없습니다. 예를 들어 디버거가 수 안전 하 게: get/set/호출 디버깅 중인 스크립트의 상태를 변경 하지 않고이 멤버입니다.|  
|fdexPropDynamicType|멤버가 동적 이며 개체의 수명 동안 변경할 수 있습니다.|  
|fdexPropCanCall|DISPATCH_METHOD를 사용 하는 방법으로 멤버를 호출할 수 있습니다.|  
|fdexPropCannotCall|DISPATCH_METHOD를 사용 하는 방법으로 멤버를 호출할 수 없습니다.|  
|fdexPropCanConstruct|멤버는 DISPATCH_CONSTRUCT를 사용 하는 생성자로 호출할 수 있습니다.|  
|fdexPropCannotConstruct|멤버는 DISPATCH_CONSTRUCT를 사용 하는 생성자로 호출할 수 없습니다.|  
|fdexPropCanSourceEvents|멤버 이벤트를 발생 시킬 수 있습니다.|  
|fdexPropCannotSourceEvents|멤버 이벤트를 발생 시킬 수 없습니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|명령 실행 성공|  
|`DISP_E_UNKNOWNNAME`|이름을 알 수 없습니다.|  
  
## <a name="example"></a>예제  
  
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
  
## <a name="see-also"></a>참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)
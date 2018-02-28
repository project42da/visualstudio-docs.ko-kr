---
title: IDispatchEx::GetDispID | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDispatchEx.GetDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetDispID method
ms.assetid: a288d63d-b08a-4540-9d9d-0bcd182eff9a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93595cd2d0f88244866ab7363ecd68c6d8073b48
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchexgetdispid"></a>IDispatchEx::GetDispID
후속 호출에서 사용할 수 있는 해당 DISPID를 단일 멤버 이름을 매핑합니다 `IDispatchEx::InvokeEx`합니다.  
  
## <a name="syntax"></a>구문  
  
```  
 HRESULT GetDispID(  
   BSTR bstrName,  
   DWORD grfdex,  
   DISPID *pid  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bstrName`  
 매핑할 이름에 전달 합니다.  
  
 `grfdex`  
 멤버 식별자를 가져오기 위한 옵션을 결정 합니다. 이 다음 값의 조합 수 있습니다.  
  
|값|의미|  
|-----------|-------------|  
|fdexNameCaseSensitive|이름 조회는 대/소문자 구분 방식으로 수행할 수 있는 요청 수입니다. 대/소문자 구분 조회를 지원 하지 않는 개체에 의해 무시 될 수 있습니다.|  
|fdexNameEnsure|이미 존재 하지 않는 경우는 멤버를 만들 수 있는지를 요청 합니다. 새 멤버를 값으로 만들 `VT_EMPTY`합니다.|  
|fdexNameImplicit|기준 개체가 명시적으로 지정 되지 않은 경우 호출자가 특정 이름의 멤버에 대 한 개체를 검색할 수 있는지를 나타냅니다.|  
|fdexNameCaseInsensitive|이름 조회에서 대/소문자 구분 방식으로 수행할 수 있는 요청 수입니다. 대/소문자 비구분 조회를 지원 하지 않는 개체에 의해 무시 될 수 있습니다.|  
  
 `pid`  
 DISPID 결과 수신 하기 위해 호출자가 할당 위치에 대 한 포인터입니다. 오류가 발생 하면 `pid` DISPID_UNKNOWN를 포함 합니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|명령 실행 성공|  
|`E_OUTOFMEMORY`|메모리가 부족 합니다.|  
|`DISP_E_UNKNOWNNAME`|이름을 알 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 `GetDispID`대신 사용할 수 `GetIDsOfNames` 지정된 된 멤버에 대 한 DISPID를 가져올 수 있습니다.  
  
 때문에 `IDispatchEx` 추가 삭제 Dispid 집합, 멤버 유지 되지 않는다는 상수 개체의 수명에 대 한 허용 합니다.  
  
 사용 하지 않는 `riid` 매개 변수에서 `IDispatch::GetIDsOfNames` 제거 되었습니다.  
  
## <a name="example"></a>예제  
  
```  
BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;   
  
   // Assign to pdex and bstrName  
   pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid);  
   // Use dispid  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)
---
title: IDispatchEx::DeleteMemberByDispID | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDispatchEx.DeleteMemberByDispID
apilocation:
- scrobj.dll
helpviewer_keywords:
- DeleteMemberByDispID method
ms.assetid: f61231e5-ba93-4ac3-bde8-d363548356b3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 573eb60dc901e43706835c4d627b25bd54bbe751
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchexdeletememberbydispid"></a>IDispatchEx::DeleteMemberByDispID
DISPID로 멤버를 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DeleteMemberByDispID(  
    DISPID id  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 멤버 식별자입니다. 사용 하 여 `GetDispID` 또는 `GetNextDispID` 디스패치 식별자를 가져올 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|명령 실행 성공|  
|`S_FALSE`|없는 멤버가 있지만 삭제할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 DISPID에 대 한 유효한 상태를 유지 해야 하는 멤버를 삭제 한 경우 `GetNextDispID`합니다.  
  
 이름이 지정 된 구성원은 삭제 하는 경우 나중에 같은 이름의 멤버가 다시 만들어질 dispid가 동일 해야 합니다. (대/소문자만 다른 구성원 이름이 "same" 지은 개체에 따라 다릅니다.)  
  
## <a name="example"></a>예제  
  
```  
BSTR bstrName;  
DISPID dispid;  
IDispatchEx *pdex;   
  
// Assign to pdex and bstrName  
if (SUCCEEDED(pdex->GetDispID(bstrName, fdexNameCaseSensitive, &dispid)))  
    pdex->DeleteMemberByDispID(dispid);  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)
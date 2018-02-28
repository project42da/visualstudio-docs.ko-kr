---
title: IDispatchEx::GetMemberName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDispatchEx.GetMemberName
apilocation:
- scrobj.dll
helpviewer_keywords:
- GetMemberName method
ms.assetid: 5e59b63c-b781-4b90-88fd-40603a379a2d
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 63489dad447ece245e14e483127cb67327d55fe5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchexgetmembername"></a>IDispatchEx::GetMemberName
멤버의 이름을 검색합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetMemberName(  
   DISPID id,  
   BSTR *pbstrName  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `id`  
 멤버를 식별합니다. 사용 하 여 `GetDispID` 또는 `GetNextDispID` 디스패치 식별자를 가져올 수 있습니다.  
  
 `pbstrName`  
 주소는 `BSTR` 멤버의 이름을 받는입니다. 호출 응용 프로그램은이 값을 해제 해야 합니다.  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|명령 실행 성공|  
|`DISP_E_UNKNOWNNAME`|이름을 알 수 없습니다.|  
  
## <a name="example"></a>예제  
  
```  
HRESULT hr;  
   BSTR bstrName;  
   DISPID dispid;  
   IDispatchEx *pdex;  
  
   // Assign to pdex  
   hr = pdex->GetNextDispID(fdexEnumAll, DISPID_STARTENUM, &dispid);  
   while (hr == NOERROR)  
   {  
      hr = pdex->GetMemberName(dispid, &bstrName);  
      if (!wcscmp(bstrName, OLESTR("Bar")))  
      {  
         SysFreeString(bstrName);  
         return TRUE;  
      }  
   SysFreeString(bstrName);  
   hr = pdex->GetNextDispID(fdexEnumAll, dispid, &dispid);  
   }  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)   
 [IDispatchEx::GetDispID](../../winscript/reference/idispatchex-getdispid.md)   
 [IDispatchEx::GetNextDispID](../../winscript/reference/idispatchex-getnextdispid.md)
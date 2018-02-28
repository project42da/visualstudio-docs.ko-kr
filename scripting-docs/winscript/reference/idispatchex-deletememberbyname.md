---
title: IDispatchEx::DeleteMemberByName | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IDispatchEx.DeleteMemberByName
apilocation:
- scrobj.dll
helpviewer_keywords:
- DeleteMemberByName method
ms.assetid: a01b4e6a-d989-4b29-bb3f-04554f8c39f7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5cb9a9dfd979954c42101fde41819d7e12db59e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idispatchexdeletememberbyname"></a>IDispatchEx::DeleteMemberByName
이름별으로 멤버를 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DeleteMemberByName(  
   BSTR bstrName,  
   DWORD grfdex  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `bstrName`  
 삭제할 멤버의 이름입니다.  
  
 `grfdex`  
 멤버 이름은 대/소문자 구분을 결정 합니다. 다음 값 중 하나일 수 있습니다 이러한.  
  
|값|의미|  
|-----------|-------------|  
|fdexNameCaseSensitive|이름 조회는 대/소문자 구분 방식으로 수행할 수 있는 요청 수입니다. 대/소문자 구분 조회를 지원 하지 않는 개체에 의해 무시 됩니다.|  
|fdexNameCaseInsensitive|이름 조회에서 대/소문자 구분 방식으로 수행할 수 있는 요청 수입니다. 대/소문자 비구분 조회를 지원 하지 않는 개체에 의해 무시 됩니다.|  
  
## <a name="return-value"></a>반환 값  
 다음 값 중 하나를 반환합니다.  
  
|||  
|-|-|  
|`S_OK`|명령 실행 성공|  
|`S_FALSE`|없는 멤버가 있지만 삭제할 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 DISPID에 대 한 유효한 상태를 유지 해야 하는 멤버를 삭제 한 경우 `GetNextDispID`합니다.  
  
 이름이 지정 된 구성원은 삭제 하는 경우 나중에 같은 이름의 멤버가 다시 만들어질 dispid가 동일 해야 합니다. (대/소문자만 다른 멤버 "동일한" 것인지 종속 개체입니다.)  
  
## <a name="example"></a>예제  
  
```  
BSTR bstrName;  
IDispatchEx *pdex;  
  
// Assign to pdex and bstrName  
pdex->DeleteMemberByName(bstrName, fdexNameCaseSensitive);  
```  
  
## <a name="see-also"></a>참고 항목  
 [IDispatchEx 인터페이스](../../winscript/reference/idispatchex-interface.md)
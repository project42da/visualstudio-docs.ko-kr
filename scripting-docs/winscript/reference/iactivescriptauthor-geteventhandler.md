---
title: IActiveScriptAuthor::GetEventHandler | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IActiveScriptAuthor.GetEventHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IActiveScriptAuthor::GetEventHandler
ms.assetid: 87c7a71d-46b9-448c-b34d-394105e20982
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b09f900162b6dba82696c946b53ab131691530c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptauthorgeteventhandler"></a>IActiveScriptAuthor::GetEventHandler
지정 된 특성이 있는 스크립틀릿을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT GetEventHandler(  
   IDispatch          *pdisp,  
   LPCOLESTR          pszItem,  
   LPCOLESTR          pszSubItem,  
   LPCOLESTR          pszEvent,  
   IScriptEntry       **ppse  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pdisp`  
 [in] `IDispatch` 개체에 해당 하는 `NamedItem` 는 스크립틀릿 연결 합니다.  
  
 `pszItem`  
 [in] 최상위 호스트에서 스크립틀릿 정규화 된 이름 식별자의 버퍼 주소입니다.  
  
 `pszSubItem`  
 [in] 호스트에서 정규화 된 스크립틀릿 이름의 2-수준 식별자의 버퍼 주소입니다. 이름에는 하나의 수준만 경우 NULL로 설정 합니다.  
  
 `pszEvent`  
 [in] 이벤트 이름을 포함 하는 버퍼의 주소입니다. 스크립틀릿에는이 이벤트에 대 한 이벤트 처리기입니다.  
  
 `ppse`  
 [out] 에 대 한 포인터를 수신 하는 변수의 주소는 `IScriptEntry` 지정 된 특성이 있는 스크립틀릿의 인터페이스입니다.  
  
## <a name="return-value"></a>반환 값  
 `HRESULT`입니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
  
## <a name="see-also"></a>참고 항목  
 [IActiveScriptAuthor 인터페이스](../../winscript/reference/iactivescriptauthor-interface.md)   
 [IScriptEntry 인터페이스](../../winscript/reference/iscriptentry-interface.md)
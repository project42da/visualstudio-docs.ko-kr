---
title: ISimpleConnectionPoint::DescribeEvents | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- ISimpleConnectionPoint.DescribeEvents
apilocation:
- pdm.dll
helpviewer_keywords:
- ISimpleConnectionPoint::DescribeEvents
ms.assetid: 659ea05f-d41e-424a-bb38-df7672b2d135
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 42dab9558d46eae0fbb640c60264a79877708321
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isimpleconnectionpointdescribeevents"></a>ISimpleConnectionPoint::DescribeEvents
이벤트의 지정된 된 범위에서 DISPID와 각 이벤트에 대 한 이름을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT DescribeEvents(  
   ULONG    iEvent,  
   ULONG    cEvents,  
   DISPID*  prgid,  
   BSTR*    prgbstr,  
   ULONG*   pcEventsFetched  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iEvent`  
 [in] 검색할 첫 번째 이벤트의 인덱스입니다.  
  
 `cEvents`  
 [in] 검색 하는 이벤트 수입니다.  
  
 `prgid`  
 [out] 이벤트 DISPID 값의 배열입니다.  
  
 `prgbstr`  
 [out] 이벤트 이름 배열입니다.  
  
 `pcEventsFetched`  
 [out] 인출 된 이벤트의 실제 수입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
|`S_FALSE`|사용할 수 있었던 것 보다 더 많은 이벤트를 요청 했습니다. 사용할 수 없는 이벤트 DISPID_NULL 및 null BSTR 표시 됩니다.|  
|`E_INVALIDARG`|요소를 가져올 수 없습니다.|  
  
## <a name="remarks"></a>설명  
 이 메서드는 이벤트의 지정된 된 범위에서 DISPID와 각 이벤트에 대 한 이름을 반환합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ISimpleConnectionPoint 인터페이스](../../winscript/reference/isimpleconnectionpoint-interface.md)
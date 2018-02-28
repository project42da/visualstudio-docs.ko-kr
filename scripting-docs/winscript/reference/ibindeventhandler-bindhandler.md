---
title: IBindEventHandler::BindHandler | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- IBindEventHandler.BindHandler
apilocation:
- scrobj.dll
helpviewer_keywords:
- IBindEventHandler::BindHandler
ms.assetid: 87909828-2224-4bb1-a6c9-dfe715ac4c9b
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 66de7cba8181ce9f3d683a90e4d7dd51e63d4779
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ibindeventhandlerbindhandler"></a>IBindEventHandler::BindHandler
개체에 이벤트를 바인딩합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT BindHandler(  
   LPCOLESTR   pstrEvent,  
   IDispatch*  pdisp  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pstrEvent`  
 [in] 이벤트 처리를 지정 합니다.  
  
 `pdisp`  
 [in] 이벤트를 처리할 개체를 지정 합니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 개체에 이벤트를 바인딩합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IBindEventHandler 인터페이스](../../winscript/reference/ibindeventhandler-interface.md)
---
title: IDebugHelper::CreatePropertyBrowser | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
apiname: IDebugHelper.CreatePropertyBrowser
apilocation: pdm.dll
helpviewer_keywords: IDebugHelper::CreatePropertyBrowser
ms.assetid: 2fa819cf-c7f7-4bd7-b018-ea33b804ba8f
caps.latest.revision: "8"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f728068b6d1db6fe70a084ae680f32a78a0a2760
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="idebughelpercreatepropertybrowser"></a>IDebugHelper::CreatePropertyBrowser
속성 브라우저를 래핑하는 VARIANT를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
HRESULT CreatePropertyBrowser(  
   VARIANT*                  pvar,  
   LPCOLESTR                 bstrName,  
   IDebugApplicationThread*  pdat,  
   IDebugProperty**          ppdob  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `pvar`  
 [in] 찾아보려면 루트 variant입니다.  
  
 `bstrName`  
 [in] 루트 부여할 이름입니다.  
  
 `pdat`  
 [in] 스레드가 요청 속성입니다. 이 매개 변수가 NULL 이면 없습니다 마샬링 수행 됩니다.  
  
 `ppdob`  
 [out] 속성 브라우저입니다.  
  
## <a name="return-value"></a>반환 값  
 이 메서드는 `HRESULT`를 반환합니다. 가능한 값에는 다음 표에 있는 값이 포함되지만, 이에 국한되는 것은 아닙니다.  
  
|값|설명|  
|-----------|-----------------|  
|`S_OK`|메서드가 성공했으며|  
  
## <a name="remarks"></a>설명  
 이 메서드는 VARIANT를 래핑하는 속성 브라우저를 반환 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [IDebugHelper::CreatePropertyBrowserEx](../../winscript/reference/idebughelper-createpropertybrowserex.md)   
 [IDebugHelper 인터페이스](../../winscript/reference/idebughelper-interface.md)   
 [IDebugProperty 인터페이스](../../winscript/reference/idebugproperty-interface.md)
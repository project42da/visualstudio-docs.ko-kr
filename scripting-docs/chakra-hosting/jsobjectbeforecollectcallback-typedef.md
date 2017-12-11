---
title: JsObjectBeforeCollectCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7d11de01c44792d3e41cc2721a404f2ed906f02e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsobjectbeforecollectcallback-typedef"></a>JsObjectBeforeCollectCallback Typedef
개체를 수집하기 전에 호출된 콜백입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `ref`  
 수집할 개체입니다.  
  
 `callbackState`  
 `JsSetObjectBeforeCollectCallback`에 전달된 상태입니다.  
  
## <a name="remarks"></a>설명  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
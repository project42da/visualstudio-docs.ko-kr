---
title: JsPromiseContinuationCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 762391cb66e5298bd70beb3238720d3717554ae0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jspromisecontinuationcallback-typedef"></a>JsPromiseContinuationCallback Typedef
프라미스 연속 콜백입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `task`  
  `callbackState`  
  
## <a name="remarks"></a>설명  
 호스트가 `JsSetPromiseContinuationCallback`에서 프라미스 연속 콜백을 지정할 수 있습니다. 스크립트에서 나중에 실행할 작업을 만드는 경우 해당 작업을 사용하여 프라미스 연속 콜백이 호출되고, 현재 스크립트 실행이 완료될 때 실행되도록 FIFO 큐에 작업이 저장되어야 합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
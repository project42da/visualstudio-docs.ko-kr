---
title: JsProjectionEnqueueCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bda4a3a80edac38ab2c3885c2256cdf9d03eb8c1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsprojectionenqueuecallback-typedef"></a>JsProjectionEnqueueCallback Typedef
프로젝션 API가 원본이 아닌 다른 스레드에서 완료될 때 JsRT에서 호출하는 응용 프로그램 콜백입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `jsCallback`  
 원래 스레드에서 호출할 콜백입니다.  
  
 `jsContext`  
 응용 프로그램 컨텍스트입니다.  
  
 `callbackState`  
 `jsCallback`에 전달되어야 하는 JsRT 컨텍스트입니다.  
  
## <a name="remarks"></a>설명  
 콜백을 받으려면 JsSetProjectionEnqueueCallback를 호출해야 합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
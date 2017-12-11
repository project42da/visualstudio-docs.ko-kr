---
title: JsProjectionCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 80d1c64f04f44a8560c25935fba2a48905a73260
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsprojectioncallback-typedef"></a>JsProjectionCallback Typedef
올바른 스레드에서 `JsProjectionEnqueueCallback` 에 전달된 컨텍스트를 사용하여 호출되어야 하는 JsRT 콜백입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `jsContext`  
 콜백을 받으려면 `JsSetProjectionEnqueueCallback` 을 호출해야 합니다.  
  
## <a name="remarks"></a>설명  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
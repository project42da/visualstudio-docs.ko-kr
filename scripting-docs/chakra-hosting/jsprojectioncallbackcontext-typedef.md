---
title: JsProjectionCallbackContext Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7548dc14ab4b3dddc1633a1ba948aba564d8438a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsprojectioncallbackcontext-typedef"></a>JsProjectionCallbackContext Typedef
올바른 스레드에서 응용 프로그램이 JsRT에서 응용 프로그램 콜백 JsProjectionEnqueueCallback에 전달한 다음 제공된 콜백 `JsProjectionCallback`에서 JsRT로 다시 전달되는 컨텍스트입니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## <a name="remarks"></a>설명  
 콜백을 받으려면 `JsSetProjectionEnqueueCallback` 을 호출해야 합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
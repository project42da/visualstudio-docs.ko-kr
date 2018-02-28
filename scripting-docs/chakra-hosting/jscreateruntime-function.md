---
title: "JsCreateRuntime 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 93a3df1e7ea76cf76fad9ffde9ccea19f2ba28af
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreateruntime-function"></a>JsCreateRuntime 함수
새 런타임을 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
// Edge mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_ JsRuntimeVersion version,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `attributes`  
 만들려는 런타임의 특성입니다.  
  
 `version`  
 만들려는 런타임의 버전입니다.  
  
 `threadService`  
 런타임에 대한 스레드 서비스입니다. null일 수 있습니다.  
  
 `runtime`  
 만들어진 런타임입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 `version` 매개 변수는 가장자리 모드에서 지원되지 않습니다. 가장자리 모드에서 이 API를 사용하는 방법에 대한 자세한 내용은 [가장자리 모드 및 레거시 엔진을 대상으로 지정](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
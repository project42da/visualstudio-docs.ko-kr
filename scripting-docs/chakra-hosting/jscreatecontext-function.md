---
title: "JsCreateContext 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee756158401468ee00007a764e18a0846f35a3dc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatecontext-function"></a>JsCreateContext 함수
스크립트를 실행하기 위한 스크립트 컨텍스트를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
// Edge mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ JsContextRef *newContext);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _In_ IDebugApplication *debugApplication,  
   _Out_ JsContextRef *newContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `runtime`  
 스크립트 컨텍스트가 만들어지는 런타임입니다.  
  
 `debugApplication`  
 디버깅에 사용할 디버그 응용 프로그램입니다. 디버깅이 컨텍스트에 대해 사용되지 않으면 이 매개 변수가 null일 수 있습니다.  
  
 `newContext`  
 만들어진 스크립트 컨텍스트입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 각 스크립트 컨텍스트에는 모든 기타 스크립트 컨텍스트에서 격리된 고유한 전역 개체가 있습니다.  
  
 `debugApplication` 매개 변수는 가장자리 모드에서 지원되지 않습니다. 가장자리 모드에서 이 API를 사용하는 방법에 대한 자세한 내용은 [가장자리 모드 및 레거시 엔진을 대상으로 지정](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)을 참조하세요.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
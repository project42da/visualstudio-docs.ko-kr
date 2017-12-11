---
title: "JsCreateFunction 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsCreateFunction
helpviewer_keywords: JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fa0b39c0475814b036784a9dbb48553d50a83ea
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatefunction-function"></a>JsCreateFunction 함수
새 JavaScript 함수를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `nativeFunction`  
 함수가 호출될 때 호출할 메서드입니다.  
  
 `callbackState`  
 다시 콜백에 전달될 사용자가 제공한 상태입니다.  
  
 `function`  
 새 함수 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 호출의 결과입니다(있는 경우).  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
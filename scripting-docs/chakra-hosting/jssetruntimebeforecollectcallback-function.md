---
title: "JsSetRuntimeBeforeCollectCallback 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 469b33a324f67d17bd6f5156da7cce169b98c663
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetruntimebeforecollectcallback-function"></a>JsSetRuntimeBeforeCollectCallback 함수
가비지 컬렉션 전에 런타임에서 호출되는 콜백 함수를 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `runtime`  
 할당 콜백을 등록할 런타임입니다.  
  
 `callbackState`  
 다시 콜백에 전달될 사용자가 제공한 상태입니다.  
  
 `beforeCollectCallback`  
 설정되는 콜백 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 콜백은 현재 런타임 스레드에서 호출되므로 콜백이 완료될 때까지 실행이 차단됩니다.  
  
 콜백은 호스트에서 가비지 수집을 준비하는 데 사용됩니다. 예를 들어 불필요한 참조 및 Chakra 개체를 해제합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
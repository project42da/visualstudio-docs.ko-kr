---
title: "JsGetAndClearException 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsGetAndClearException
helpviewer_keywords: JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3e7e4f89bac59aa776762586ab20fa831b5c24bf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetandclearexception-function"></a>JsGetAndClearException 함수
현재 컨텍스트의 런타임을 예외 상태로 만든 예외를 반환하고 해당 런타임의 예외 상태를 다시 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `exception`  
 현재 컨텍스트의 런타임에 대한 예외입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 현재 컨텍스트의 런타임이 예외 상태가 아닐 경우 이 API에서 `JsErrorInvalidArgument`를 반환합니다. 런타임이 사용되지 않으면 스크립트가 종료되었음을 나타내는 예외를 반환하지만, 예외를 지우지 않습니다. `JsEnableRuntimeExecution`을 사용하여 런타임을 다시 사용하도록 설정하면 예외가 지워집니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
---
title: "JsHasException 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsHasException
helpviewer_keywords: JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 32334f4b8787bebaffb9553fcdd40f85334462cb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jshasexception-function"></a>JsHasException 함수
현재 컨텍스트의 런타임이 예외 상태인지를 결정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `hasException`  
 현재 컨텍스트의 런타임이 예외 상태인지를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 런타임에 대한 호출로 인해 예외가 발생하면(스크립트 실행의 결과로 또는 변환 실패 같은 문제로 인해) 런타임이 "예외 상태"로 전환됩니다. 예외 API를 제외하고 런타임에서 생성된 컨텍스트에 대한 모든 호출이 예외가 지워질 때까지 `JsErrorInExceptionState`와 함께 실패합니다.  
  
 콜백이 엔진으로 돌아갈 때까지 현재 컨텍스트의 런타임이 예외 상태이면 엔진이 자동으로 예외를 다시 throw합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
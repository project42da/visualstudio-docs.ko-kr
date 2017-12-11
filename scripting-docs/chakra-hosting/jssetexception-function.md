---
title: "JsSetException 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsSetException
helpviewer_keywords: JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5d8fce71f14dedea02e1809fb72281f575f60604
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetexception-function"></a>JsSetException 함수
현재 컨텍스트의 런타임을 예외 상태로 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `exception`  
 현재 컨텍스트의 런타임에 대해 설정할 JavaScript 예외입니다.  
  
## <a name="return-value"></a>반환 값  
 엔진이 예외 상태로 설정될 경우 `JsNoError`이며, 그렇지 않을 경우 실패 코드입니다.  
  
## <a name="remarks"></a>설명  
 현재 컨텍스트의 런타임이 이미 예외 상태일 경우 이 API에서 `JsErrorInExceptionState`를 반환합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
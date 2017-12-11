---
title: "JsCreateArray 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsCreateArray
helpviewer_keywords: JsCreateArray function
ms.assetid: a119949a-e427-4349-9d00-5ec20fb9319c
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0e57724b008c13e5340626074325998b0a63fa9a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatearray-function"></a>JsCreateArray 함수
Javascript 배열 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsCreateArray(  
   _In_ unsigned int length,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `length`  
 배열의 초기 길이입니다.  
  
 `result`  
 새 배열 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
---
title: "JsGetOwnPropertyNames 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsGetOwnPropertyNames
helpviewer_keywords: JsGetOwnPropertyNames function
ms.assetid: 0c17ea06-b17f-4ea3-ad04-1259a4d1b6de
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4efd4133fb2636afdacba205f7be1ba7980a36c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetownpropertynames-function"></a>JsGetOwnPropertyNames 함수
개체에 대한 모든 속성 목록을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsGetOwnPropertyNames(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *propertyNames  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 속성 이름을 가져올 소스 개체입니다.  
  
 `propertyNames`  
 속성 이름 배열입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
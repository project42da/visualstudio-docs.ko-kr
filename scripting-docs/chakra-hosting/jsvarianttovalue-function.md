---
title: "JsVariantToValue 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsVariantToValue
helpviewer_keywords: JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc778d87aab7e80e7c1b04a68c2d3b9c6fdd885a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsvarianttovalue-function"></a>JsVariantToValue 함수
전달된 `VARIANT`의 프로젝션인 JavaScript 값을 생성합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `variant`  
 프로젝션해야 하는 `VARIANT`입니다.  
  
 `value`  
 `VARIANT`의 프로젝션인 JavaScript 값입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 프로젝션된 값은 스크립트에서 COM 자동화 개체를 호출하는 데 스크립트가 사용할 수 있습니다. 호스트는 COM 스레딩 규칙 적용을 담당합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
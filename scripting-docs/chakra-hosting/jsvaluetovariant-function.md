---
title: "JsValueToVariant 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2beb0a72a8e19d38d80ab8bf29ce0478ba7f481f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsvaluetovariant-function"></a>JsValueToVariant 함수
전달된 `VARIANT`를 JavaScript 값의 프로젝션으로 초기화합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 `VARIANT`로 프로젝트할 JavaScript 값입니다.  
  
 `variant`  
 프로젝션으로 초기화될 `VARIANT` 구조체에 대한 포인터입니다.  
  
## <a name="return-value"></a>반환 값  
  
## <a name="remarks"></a>설명  
 프로젝션 `VARIANT`는 COM 자동화 클라이언트에서 프로젝션된 JavaScript 개체를 호출하는 데 사용할 수 있습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
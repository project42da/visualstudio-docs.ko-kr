---
title: "JsDefineProperty 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsDefineProperty
helpviewer_keywords: JsDefineProperty function
ms.assetid: b2cf48d6-eb40-457c-aa8b-b16a50dc5d6a
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f929dd875b2ba8bf95db8d5970a770ce2859484
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsdefineproperty-function"></a>JsDefineProperty 함수
속성 설명자를 기반으로 새 개체의 속성을 정의합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsDefineProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef propertyDescriptor,  
   _Out_ bool *result  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 속성이 있는 개체입니다.  
  
 `propertyId`  
 속성의 ID입니다.  
  
 `propertyDescriptor`  
 속성 설명자입니다.  
  
 `result`  
 속성이 정의되었는지를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
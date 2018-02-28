---
title: "JsDeleteProperty 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsDeleteProperty
helpviewer_keywords:
- JsDeleteProperty function
ms.assetid: 0f6ac6a7-3576-42f5-98d0-1c06542c8149
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 60a6da027fe128d91770bbf2d299d5d23de6d3eb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsdeleteproperty-function"></a>JsDeleteProperty 함수
개체의 속성을 삭제합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsDeleteProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ bool useStrictRules,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `object`  
 속성이 포함된 개체입니다.  
  
 `propertyId`  
 속성의 ID입니다.  
  
 `useStrictRules`  
 속성 집합은 strict 모드 규칙을 따라야 합니다.  
  
 `result`  
 속성이 삭제되었는지를 나타냅니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
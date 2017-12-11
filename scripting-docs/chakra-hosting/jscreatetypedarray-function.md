---
title: "JsCreateTypedArray 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1df33d0e1aadec9d7ed5aebf743e2c2f840e51fd
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatetypedarray-function"></a>JsCreateTypedArray 함수
JavaScript 형식화된 배열 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayType`  
 만들려는 배열의 형식입니다.  
  
 `baseArray`  
 새 배열의 기본 배열입니다. 기본 배열이 없는 경우 `JS_INVALID_REFERENCE`를 사용합니다.  
  
 `byteOffset`  
 결과 형식화된 배열에 대한 `baseArray`(`ArrayBuffer`) 시작 부분부터 참조까지의 오프셋(바이트)입니다. `baseArray`가 `ArrayBuffer` 개체인 경우에만 적용할 수 있습니다. 그렇지 않은 경우 0이어야 합니다.  
  
 `elementLength`  
 배열의 요소 수입니다. `baseArray` 없이 새 형식화된 배열을 만드는 경우(`baseArray`가 `JS_INVALID_REFERENCE`인 경우) 또는 `baseArray`가 `ArrayBuffer` 개체인 경우에만 적용할 수 있습니다. 그렇지 않은 경우 0이어야 합니다.  
  
 `result`  
 새 형식화된 배열 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 `baseArray`는 `ArrayBuffer`, 다른 형식화된 배열 또는 JavaScript `Array`일 수 있습니다. 반환된 형식화된 배열은 `ArrayBuffer`인 경우`baseArray`를 사용하거나, 그렇지 않은 경우 기본 소스 배열의 복사본을 만들어 사용합니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
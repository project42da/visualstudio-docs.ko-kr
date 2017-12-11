---
title: "JsGetTypedArrayStorage 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b6f4dc99c219c2ebba631c42493bc194148b497
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsgettypedarraystorage-function"></a>JsGetTypedArrayStorage 함수
형식화된 배열에서 사용되는 기본 메모리 저장소를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `typedArray`  
 형식화된 배열 인스턴스입니다.  
  
 `buffer`  
 배열의 버퍼입니다. 반환되는 버퍼의 수명은 배열의 수명과 같습니다. 버퍼 포인터는 가비지 컬렉션을 위한 배열에 대한 참조로 계산되지 않습니다.  
  
 `bufferLength`  
 버퍼의 바이트 수입니다.  
  
 `arrayType`  
 배열의 형식입니다.  
  
 `elementSize`  
 배열의 요소 크기입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
---
title: "JsCreateDataView 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e5150a9b858e09217ee7ac3c1f25efba36615f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscreatedataview-function"></a>JsCreateDataView 함수
Javascript `DataView` 개체를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayBuffer`  
 결과 `DataView` 개체에 대한 저장소로 사용할 기존 `ArrayBuffer` 개체입니다.  
  
 `byteOffset`  
 결과 `DataView`에 대한 `arrayBuffer` 시작 부분부터 참조까지의 오프셋(바이트)입니다.  
  
 `byteLength`  
 결과 DataView에 대한 ArrayBuffer에서 참조까지의 바이트 수입니다.  
  
 `result`  
 새 DataView 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 가장자리 모드에서만 지원됩니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
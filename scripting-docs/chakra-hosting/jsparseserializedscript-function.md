---
title: "JsParseSerializedScript 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsParseSerializedScript
helpviewer_keywords: JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7eb18c8537d7bdfe69969293b66a5909ba7c3fa1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsparseserializedscript-function"></a>JsParseSerializedScript 함수
serialize된 스크립트를 구문 분석하고 스크립트를 나타내는 함수를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `script`  
 구문 분석할 스크립트입니다.  
  
 `buffer`  
 serialize된 스크립트입니다.  
  
 `sourceContext`  
 디버깅 가능한 스크립트 컨텍스트에서 사용될 수 있는 스크립트를 식별하는 쿠키입니다.  
  
 `sourceUrl`  
 스크립트를 가져온 위치입니다.  
  
 `result`  
 스크립트 코드를 나타내는 함수입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 버퍼가 스크립팅 엔진에 의해 메모리에서 지속되지 않으므로 버퍼가 스크립트를 실행하는 데 사용될 수 있는 동안에는 코드에서 버퍼를 활성 상태로 유지해야 합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
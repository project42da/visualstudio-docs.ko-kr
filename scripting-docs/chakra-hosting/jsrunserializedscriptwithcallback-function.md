---
title: "JsRunSerializedScriptWithCallback 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ce51c9473100e71831dd53cc6572d9740790ffa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsrunserializedscriptwithcallback-function"></a>JsRunSerializedScriptWithCallback 함수
serialize된 스크립트를 실행합니다.     필요한 경우에만 스크립트 원본을 지연 로드하는 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
);  
  
```  
  
#### <a name="parameters"></a>매개 변수  
 `scriptLoadCallback`  
 스크립트의 소스 코드를 로드해야 할 때 콜백이 호출됩니다.  
  
 `scriptUnloadCallback`  
 serialize된 스크립트 및 소스 코드가 더 이상 필요하지 않을 때 콜백이 호출됩니다.  
  
 `buffer`  
 serialize된 스크립트입니다.  
  
 `sourceContext`  
 디버깅 가능한 스크립트 컨텍스트에서 사용될 수 있는 스크립트를 식별하는 쿠키입니다.     이 컨텍스트가 scriptLoadCallback 및 scriptUnloadCallback으로 전달됩니다.  
  
 `sourceUrl`  
 스크립트를 가져온 위치입니다.  
  
 `result`  
 스크립트를 실행한 결과입니다(있는 경우). 이 매개 변수는 null일 수 있습니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
  
> [!NOTE]
>  이 API는 아직 스토어 앱에서 사용할 수 없습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 버퍼를 통해 생성된 함수의 모든 인스턴스가 가비지 수집될 때까지 런타임이 버퍼에 유지됩니다.  그런 다음 scriptUnloadCallback을 호출하여 안전하게 해제할 수 있음을 호출자에게 알립니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
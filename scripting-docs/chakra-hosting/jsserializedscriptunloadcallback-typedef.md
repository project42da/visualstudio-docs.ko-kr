---
title: JsSerializedScriptUnloadCallback typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6f485d31367f189231d354c653c8e58cc8656eb9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsserializedscriptunloadcallback-typedef"></a>JsSerializedScriptUnloadCallback typedef
스크립트 실행과 관련된 모든 리소스를 완료하면 런타임에서 호출됩니다.     이때 바이트 코드, 컨텍스트 등 소스가 로드되면 호출자는 소스를 해제해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `sourceContext`  
 `JsParseSerializedScriptWithCallback` 또는 `JsRunSerializedScriptWithCallback`에 전달된 컨텍스트입니다.  
  
## <a name="remarks"></a>설명  
  
> [!WARNING]
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
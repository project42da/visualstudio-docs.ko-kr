---
title: JsSerializedScriptLoadSourceCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0ff3bc206cf3779023a13166f30e8f4f719e7ebe
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsserializedscriptloadsourcecallback-typedef"></a>JsSerializedScriptLoadSourceCallback Typedef
Serialize된 스크립트의 소스 코드를 로드하기 위해 런타임에서 호출됩니다.     호출자는 `JsSerializedScriptUnloadCallback`까지 스크립트 버퍼를 유효하게 유지해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `sourceContext`  
 `JsParseSerializedScriptWithCallback` 또는 `JsRunSerializedScriptWithCallback`에 전달된 컨텍스트입니다.  
  
 `scriptBuffer`  
 반환된 스크립트입니다.  
  
## <a name="remarks"></a>설명  
  
> [!WARNING]
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
---
title: "JsGetRuntimeMemoryLimit 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6373e166ff4efe6bc8c5a33d203d60647c4be9b7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsgetruntimememorylimit-function"></a>JsGetRuntimeMemoryLimit 함수
런타임에 대한 현재 메모리 제한을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `runtime`  
 메모리 제한을 검색할 런타임입니다.  
  
 `memoryLimit`  
 런타임의 현재 메모리 제한(바이트 단위) 또는 제한이 설정되지 않은 경우 -1  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 런타임이 다른 스레드에서 활성인지 아닌지에 관계없이 런타임의 메모리 제한은 항상 검색할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
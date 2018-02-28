---
title: "JsSetRuntimeMemoryAllocationCallback 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 755ab36c8edb8c0350eb2b245e060344c8825dee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jssetruntimememoryallocationcallback-function"></a>JsSetRuntimeMemoryAllocationCallback 함수
지정된 런타임에 대한 메모리 할당 콜백을 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `runtime`  
 할당 콜백을 등록할 런타임입니다.  
  
 `callbackState`  
 다시 콜백에 전달될 사용자가 제공한 상태입니다.  
  
 `allocationCallback`  
 메모리 할당 이벤트에 대해 호출할 메모리 할당 콜백입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 메모리 할당 콜백을 등록하면 런타임이 OS에서 메모리를 획득하거나 OS로 메모리를 해제할 때마다 호스트로 콜백합니다. 콜백 루틴은 런타임 메모리 관리자가 메모리 블록을 할당하기 전에 호출됩니다. 콜백이 false를 반환하면 할당이 거부됩니다. 런타임 메모리 관리자도 메모리를 블록을 해제한 후와 할당 실패 후에 콜백 루틴을 호출합니다.  
  
 콜백은 현재 런타임 스레드에서 호출되므로 콜백이 완료될 때까지 실행이 차단됩니다.  
  
 콜백 반환 값은 저장되지 않습니다. 이전에 거부된 할당으로 인해 런타임은 나중에 새 메모리 할당을 위해 콜백을 다시 호출하지 못합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
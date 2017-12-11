---
title: JsMemoryAllocationCallback Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9672c23f48a2cb3e20de58012b267b30f4514d66
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsmemoryallocationcallback-typedef"></a>JsMemoryAllocationCallback Typedef
메모리 호출 이벤트에 대해 사용자가 구현한 콜백 루틴입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 callbackState  
 JsSetRuntimeMemoryAllocationCallback에 전달된 상태입니다.  
  
 allocationEvent  
 형식 할당 이벤트의 형식입니다.  
  
 allocationSize  
 할당의 크기입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 JsMemoryAllocate 이벤트의 경우 true를 반환하면 런타임에서 할당을 계속할 수 있습니다. false를 반환하면 할당 요청이 거부됨을 나타냅니다. 다른 할당 이벤트에 대해서는 반환 값이 무시됩니다.  
  
## <a name="remarks"></a>설명  
 이 콜백을 등록하려면 JsSetRuntimeMemoryAllocationCallback을 사용합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
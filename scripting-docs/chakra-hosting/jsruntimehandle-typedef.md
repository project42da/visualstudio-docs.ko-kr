---
title: JsRuntimeHandle Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d3c0344e203c58691048c55ba4080c6c86c1c643
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsruntimehandle-typedef"></a>JsRuntimeHandle Typedef
Chakra 런타임에 대한 핸들입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef void *JsRuntimeHandle;  
```  
  
## <a name="remarks"></a>설명  
 각 Chakra 런타임에는 고유한 독립 실행 엔진, JIT 컴파일러 및 가비지 수집 힙이 포함되어 있습니다. 따라서 각 런타임은 다른 런타임에서 완전히 격리됩니다.  
  
 런타임은 모든 스레드에서 사용될 수 있지만 언제든지 하나의 스레드만 런타임을 호출할 수 있습니다.  
  
> [!WARNING]
>  Chakra 호스팅 API의 다른 개체 참조와 달리 JsRuntimeHandle은 가비지 수집 힙을 자체적으로 포함하고 있기 때문에 가비지 수집되지 않습니다. 런타임은 JsDisposeRuntime이 호출될 때까지 계속 존재합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
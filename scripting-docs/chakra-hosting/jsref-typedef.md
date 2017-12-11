---
title: JsRef Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d9d4c478a45f53e83dfa59fdde21cfa4c988c92e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsref-typedef"></a>JsRef Typedef
Chakra 가비지 수집기가 소유한 개체에 대한 참조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef void *JsRef;  
```  
  
## <a name="remarks"></a>설명  
 Chakra 런타임은 JsRef 참조가 지역 변수 또는 매개 변수(예: 스택의 경우)에 저장되어 있는 한, JsRef 참조를 자동적으로 추적합니다. JsRef를 스택 이외의 다른 위치에 저장하려면 JsAddRef 및 JsRelease를 호출하여 개체의 수명을 관리해야 하며, 그렇지 않으면 가비지 컬렉션이 개체가 여전히 사용 중인 동안 해당 개체를 해제할 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
---
title: JsContextRef Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ec1300717b59c3b901665b39ca0102988e83e853
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jscontextref-typedef"></a>JsContextRef Typedef
스크립트 컨텍스트에 대한 참조입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef JsRef JsContextRef;  
```  
  
## <a name="remarks"></a>설명  
 각 스크립트 컨텍스트에는 다른 스크립트 컨텍스트의 전역 개체와 다른 고유한 전역 개체가 포함되어 있습니다.  
  
 많은 Chakra 호스팅 API에는 "활성" 스크립트 컨텍스트가 필요하며, 이러한 스크립트 컨텍스트는 `JsSetCurrentContext`를 사용하여 설정할 수 있습니다. 현재 컨텍스트를 설정해야 하는 Chakra 호스팅 API는 해당 문서에 이러한 내용을 명시적으로 언급합니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
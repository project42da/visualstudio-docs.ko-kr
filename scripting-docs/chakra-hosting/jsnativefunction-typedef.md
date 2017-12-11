---
title: JsNativeFunction Typedef | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33cf475dd6a17434ea132647b7d8bde833f0de9e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsnativefunction-typedef"></a>JsNativeFunction Typedef
함수 콜백입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 callee  
 호출할 함수를 나타내는 `Function` 개체입니다.  
  
 isConstructCall  
 일반적인 호출인지 '새' 호출인지를 나타냅니다.  
  
 arguments  
 호출에 대한 인수입니다.  
  
 argumentCount  
 인수의 수입니다.  
  
## <a name="property-valuereturn-value"></a>속성 값/반환 값  
 호출의 결과입니다(있는 경우).  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
---
title: "JsStopProfiling 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsStopProfiling
helpviewer_keywords: JsStopProfiling function
ms.assetid: 3639c04f-a0f9-418b-be39-92f64b4e7ef8
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bed003e848a7ac34100a322275be04213da76e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsstopprofiling-function"></a>JsStopProfiling 함수
현재 컨텍스트에서 프로파일링을 중지합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsStopProfiling(  
   _In_ HRESULT reason  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `reason`  
 프로파일러 콜백에 전달할 프로파일링을 중지하는 이유입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 프로파일링 시작되지 않은 경우 오류를 반환하지 않습니다.  
  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 데스크톱 앱에서 지원되지만 스토어 앱에서는 지원되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
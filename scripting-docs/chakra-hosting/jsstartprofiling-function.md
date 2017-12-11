---
title: "JsStartProfiling 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsStartProfiling
helpviewer_keywords: JsStartProfiling function
ms.assetid: 638da395-42dd-4fc5-b581-819e647e887d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 964e9f26de9cb5000884089da0b404b8d22fdd8d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsstartprofiling-function"></a>JsStartProfiling 함수
현재 컨텍스트에서 프로파일링을 시작합니다.  
  
## <a name="syntax"></a>구문  
  
```  
STDAPI_(JsErrorCode) JsStartProfiling(  
   _In_ IActiveScriptProfilerCallback *callback,  
   _In_ PROFILER_EVENT_MASK eventMask,  
   _In_ unsigned long context  
);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `callback`  
 사용할 프로파일링 콜백입니다.  
  
 `eventMask`  
 콜백할 프로파일 이벤트입니다.  
  
 `context`  
 프로파일링 콜백에 전달할 컨텍스트입니다.  
  
## <a name="return-value"></a>반환 값  
 작업에 성공한 경우 코드 `JsNoError` 이고, 그렇지 않은 경우 오류 코드입니다.  
  
## <a name="remarks"></a>설명  
 활성 스크립트 컨텍스트가 필요합니다.  
  
 이 API는 데스크톱 앱에서 지원되지만 스토어 앱에서는 지원되지 않습니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
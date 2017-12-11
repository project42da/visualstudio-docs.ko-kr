---
title: "JsIsRuntimeExecutionDisabled 함수 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords: JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4827205a33d337445faf9b0e9812133f0de3e97
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsisruntimeexecutiondisabled-function"></a>JsIsRuntimeExecutionDisabled 함수
런타임에 스크립트 실행이 비활성화되었는지 여부를 나타내는 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `runtime`  
 실행이 비활성화되었는지 확인하기 위해 런타임을 지정합니다.  
  
 `isDisabled`  
 실행이 비활성화되어 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="return-value"></a>반환 값  
 작업이 성공한 경우 `JsNoError`이며 그렇지 않으면 실패 코드입니다.  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
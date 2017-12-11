---
title: "JsRuntimeAttributes 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: jsrt/JsRuntimeAttributes
helpviewer_keywords: JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3a7917ad5468b8d2924526f953ae444c5d8381eb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jsruntimeattributes-enumeration"></a>JsRuntimeAttributes 열거형
런타임 특성입니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum JsRuntimeAttributes;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|런타임에서 신뢰할 수 있는 스크립트 중단을 지원해야 합니다. 그러면 런타임 성능의 양이 적어지는 대신 런타임에서 스크립트 중단 요청을 확인하는 자릿수가 증가합니다.|  
|`JsRuntimeAttributeDisableBackgroundWork`|런타임에서 백그라운드 스레드에 대한 작업(예: 가비지 수집)을 수행하지 않습니다.|  
|`JsRuntimeAttributeDisableEval`|`eval` 또는 `function` 생성자를 사용하면 예외가 throw됩니다.|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|런타임에서 네이티브 코드를 생성하지 않습니다.|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|런타임에는 모든 실험적 기능을 사용할 수 있습니다.|  
|`JsRuntimeAttributeEnableIdleProcessing`|호스트에서 `JsIdle`을 호출하여 유휴 프로세스가 활성화됩니다. 그렇지 않으면 런타임에서 조금 더 적극적으로 메모리를 관리합니다.|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|또한 `JsSetException` 을 호출하면 예외를 스크립트 디버거(있는 경우)에 디스패치하여 예외가 발생할 때 중단할 수 있는 기회를 디버거에 제공합니다.|  
|`JsRuntimeAttributeNone`|특별한 특성이 없습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
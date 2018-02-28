---
title: "JsErrorCode 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b09babd38505c5619f414d2e349cd52b3596ceac
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="jserrorcode-enumeration"></a>JsErrorCode 열거형
Chakra 호스팅 API에서 반환된 오류 코드입니다.  
  
## <a name="syntax"></a>구문  
  
```  
enum JsErrorCode : unsigned int;  
```  
  
## <a name="members"></a>멤버  
  
### <a name="values"></a>값  
  
|이름|설명|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|컨텍스트가 이미 디버그 상태이기 때문에 디버그 상태로 넣을 수 없습니다.|  
|`JsErrorAlreadyProfilingContext`|컨텍스트가 이미 프로파일링하고 있으므로 프로파일링을 시작할 수 없습니다.|  
|`JsErrorArgumentNotObject`|개체 값에 대해 작동하는 호스팅 API를 개체가 아닌 값으로 호출했습니다.|  
|`JsErrorBadSerializedScript`|잘못 serialize된 스크립트를 사용했거나 serialize된 스크립트를 다른 버전의 Chakra 엔진으로 serialize했습니다.|  
|`JsErrorCannotDisableExecution`|런타임은 신뢰할 수 있는 스크립트 중단을 지원하지 않습니다.|  
|`JsErrorCannotSerializeDebugScript`|스크립트를 디버그 컨텍스트에서 serialize할 수 없습니다.|  
|`JsErrorCategoryEngine`|엔진 자체 내에서 발생하는 오류와 관련된 오류 범주입니다.|  
|`JsErrorCategoryFatal`|치명적이고 엔진의 실패를 나타내는 오류 범주입니다.|  
|`JsErrorCategoryScript`|스크립트에서 오류와 관련된 오류 범주입니다.|  
|`JsErrorCategoryUsage`|API 자체의 잘못된 사용과 관련된 오류 범주입니다.|  
|`JsErrorFatal`|엔진에 치명적인 오류가 발생했습니다.|  
|`JsErrorHeapEnumInProgress`|힙 열거형이 스크립트 컨텍스트에서 현재 진행 중입니다.|  
|`JsErrorIdleNotEnabled`|호스트가 유휴 프로세스를 활성화하지 않은 때 받는 유휴 알림입니다.|  
|`JsErrorInDisabledState`|런타임이 비활성 상태입니다.|  
|`JsErrorInExceptionState`|엔진이 예외 상태이며 예외를 지울 때까지 API를 호출할 수 없습니다.|  
|`JsErrorInObjectBeforeCollectCallback`|수집 콜백 전에는 개체에서 작업을 지원하지 않습니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsErrorInProfileCallback`|스크립트 컨텍스트가 프로필 콜백의 중간에 있습니다.|  
|`JsErrorInThreadServiceCallback`|스레드 서비스 콜백이 현재 진행 중입니다.|  
|`JsErrorInvalidArgument`|호스팅 API에 대한 인수를 사용할 수 없습니다.|  
|`JsErrorNoCurrentContext`|호스팅 API에서 현재 컨텍스트가 필요하지만 현재 컨텍스트가 없습니다.|  
|`JsErrorNotImplemented`|호스팅 API를 아직 구현하지 않았습니다.|  
|`JsErrorNullArgument`|null이 허용되지 않는 컨텍스트에서 호스팅 API에 대한 인수가 null입니다.|  
|`JsErrorObjectNotInspectable`|개체는 `IInspectable` 포인터에 대해 래핑 해제할 수 없습니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsErrorOutOfMemory`|Chakra 엔진에 메모리가 부족합니다.|  
|`JsErrorPropertyNotSymbol`|기호 속성에 대해 작동하는 호스팅 API를 기호가 아닌 속성 ID로 호출했습니다. 기호가 아닌 속성 ID로 함수가 호출되면 `JsGetSymbolFromPropertyId` 에서 오류 코드가 반환됩니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsErrorPropertyNotString`|문자열 속성에 대해 작동하는 호스팅 API를 문자열이 아닌 속성 ID로 호출했습니다. 문자열이 아닌 속성 ID로 함수가 호출되면 기존 `JsGetPropertyNamefromId` 에서 오류 코드가 반환됩니다.<br /><br /> 이 열거형 값은 가장자리 모드에서만 지원됩니다.|  
|`JsErrorRuntimeInUse`|아직 사용 중인 런타임을 삭제할 수 없습니다.|  
|`JsErrorScriptCompile`|JavaScript를 컴파일하지 못했습니다.|  
|`JsErrorScriptEvalDisabled`|`eval` 또는 `function` 을 사용하려 했기 때문에 스크립트가 종료되었고 eval이 비활성화되었습니다.|  
|`JsErrorScriptException`|스크립트를 실행하는 동안 JavaScript 예외가 발생했습니다.|  
|`JsErrorScriptTerminated`|런타임을 일시 중단하려는 요청으로 인해 스크립트가 종료되었습니다.|  
|`JsErrorWrongRuntime`|호스팅 API가 다른 JavaScript 런타임에 만들어진 개체와 함께 호출되었습니다.|  
|`JsErrorWrongThread`|호스팅 API가 잘못된 스레드에서 호출되었습니다.|  
|`JsNoError`|성공 오류 코드입니다.|  
  
## <a name="requirements"></a>요구 사항  
 **헤더:** jsrt.h  
  
## <a name="see-also"></a>참고 항목  
 [참조(JavaScript 런타임)](../chakra-hosting/reference-javascript-runtime.md)
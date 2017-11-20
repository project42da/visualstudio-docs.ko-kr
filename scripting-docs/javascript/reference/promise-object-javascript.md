---
title: "Promise 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 358ad98b-f7fa-448c-9ee0-ef1e2a45e9c6
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 61e5611dd0d455c7e7b704777cc2341ca43a2404
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="promise-object-javascript"></a>Promise 개체(JavaScript)
아직 계산되지 않은 값에 대해 수행할 작업을 예약하는 메커니즘을 제공합니다. 비동기 API와의 상호 작용을 관리하기 위한 추상화입니다.  
  
## <a name="syntax"></a>구문  
  
```  
var promise = new Promise(function(resolve, reject) { ... });  
```  
  
#### <a name="parameters"></a>매개 변수  
 `promise`  
 필수 요소. 프라미스가 할당되는 변수 이름입니다.  
  
 `resolve`  
 필수 요소. 프라미스가 성공적으로 완료되었음을 나타내기 위해 실행되는 함수입니다.  
  
 `reject`  
 선택적 요소. 오류가 발생하여 프라미스가 거부되었음을 나타내기 위해 실행되는 함수입니다.  
  
## <a name="remarks"></a>설명  
 프라미스는 값과 함께 완료되거나 이유와 함께 거부되어야 합니다. Promise 개체의 `then` 메서드는 프라미스가 완료되거나 거부될 경우 어느 동작이라도 먼저 발생할 때 실행됩니다. 프라미스가 성공적으로 완료되면 `then` 메서드의 처리 처리기 함수가 실행됩니다. 프라미스가 거부되면 `then` 메서드(또는 `catch` 메서드)의 오류 처리가 함수가 실행됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 프라미스를 반환하는 함수(`timeout`)를 호출하는 방법을 보여 줍니다. `then` 메서드의 처리 처리기는 5000ms 시간 제한 기간이 만료된 후 실행됩니다.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
// Note: This code uses arrow function syntax  
var m = timeout(5000).then(() => {  
    console.log("done!");  
})  
  
// Output (after 5 seconds):  
// done!  
```  
  
## <a name="example"></a>예제  
 다음 코드와 같이 `then` 메서드 호출을 연결할 수도 있습니다. 연결을 지원하려면 각 완료 처리기 자체가 프라미스를 반환해야 합니다. 동일한 `timeout` 함수를 호출하는 이 코드에서 첫 번째 timeout 호출은 1000ms 후에 반환됩니다. 첫 번째 완료 처리기가 `timeout`을 다시 호출하고, 이 프라미스는 2000ms 후에 반환됩니다. 그런 다음 완료 처리기에서 오류가 발생합니다. 오류 처리기가 `Promise.all`을 호출하고, timeout 호출이 둘 다 완료되거나 거부된 경우에만 반환됩니다.  
  
```JavaScript  
var p = timeout(1000).then(() => {  
    return timeout(2000);  
}).then(() => {  
    throw new Error("error");  
}).catch(err => {  
    return Promise.all([timeout(100), timeout(200)]);  
})  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="functions"></a>함수  
 다음 표에서는 `Promise` 개체의 함수를 설명합니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[Promise.all 함수](../../javascript/reference/promise-all-function-promise.md)|둘 이상의 프라미스를 조인하고, 지정된 모든 프라미스가 완료되거나 거부된 경우에만 반환됩니다.|  
|[Promise.race 함수](../../javascript/reference/promise-race-function-promise.md)|첫 번째 프라미스와 동일한 결과 값으로 해결되거나 거부되는 새 프라미스를 만들어 전달된 인수에서 해결하거나 거부합니다.|  
|[Promise.reject 함수](../../javascript/reference/promise-reject-function-promise.md)|전달된 인수와 동일한 결과로 거부된 새 프라미스를 만듭니다.|  
|[Promise.resolve 함수](../../javascript/reference/promise-resolve-function-promise.md)|결과가 해당 인수와 같은 해결된 프라미스를 새로 만듭니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `Promise` 개체의 메서드를 설명합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[catch 메서드](../../javascript/reference/catch-method-promise.md)|프라미스 거부 시 수행할 작업을 지정할 수 있습니다.|  
|[then 메서드](../../javascript/reference/then-method-promise.md)|프라미스 처리 시 수행할 작업을 지정할 수 있습니다.|
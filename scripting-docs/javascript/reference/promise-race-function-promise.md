---
title: "Promise.race 함수 (Promise) | Microsoft Docs"
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
ms.assetid: 9236eced-d313-4d03-8c3e-d89d762b3084
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d35c448ad143facdcd783df0551505e440521b98
ms.sourcegitcommit: 11740fed01cc602252ef698aaa11c07987b00570
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/12/2018
---
# <a name="promiserace-function-promise"></a>Promise.race 함수(Promise)
첫 번째 프라미스와 동일한 결과 값으로 해결되거나 거부되는 새 프라미스를 만들어 전달된 인수에서 해결하거나 거부합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Promise.race(iterable)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `iterable`  
 필수. 하나 이상의 프라미스입니다.  
  
## <a name="remarks"></a>설명  
 `iterable`의 프라미스 중 하나가 이미 해결 또는 거부된 상태이면 `Promise.race`는 해당 프라미스 해결(또는 거부)에 사용된 값과 동일한 결과 값을 사용하여 동일한 방식으로 해결 또는 거부된 프라미스를 반환합니다. `iterable`의 여러 프라미스가 이미 해결 또는 거부된 경우 `Promise.race`는 동일한 방식으로 해결된 프라미스를 반복되는 첫 번째 프라미스로 반환합니다. 해결 또는 거부된 반복 가능한 개체의 프라미스가 없으면 `Promise.race`에서 반환된 프라미스가 해결 또는 거부되지 않습니다.  
  
## <a name="example"></a>예  
  
```JavaScript  
var p1 = new Promise(function(resolve, reject) {  
    setTimeout(resolve, 0, 'success');  
});  
var p2 = new Promise(function(resolve, reject) { });  
var p3 = new Promise(function(resolve, reject) { });  
  
var race = Promise.race( [p1, p2, p3] );  
race.then(function(result) {  
    console.log(result);  
});  
  
// Output:  
// success  
  
var race = Promise.race( [Promise.reject('failure'),  
    Promise.resolve('success')] );  
race.catch(function(result) {  
    console.log(result);  
});  
  
// Output:  
// failure  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)

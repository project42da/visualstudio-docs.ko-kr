---
title: "Promise.all 함수 (Promise) | Microsoft Docs"
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
ms.assetid: 02a7b90c-96f6-4484-9466-d261efa1b494
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 997a419a990b407ae018f7da39fd75673ea28b6d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="promiseall-function-promise"></a>Promise.all 함수(Promise)
둘 이상의 프라미스를 조인하고, 지정된 모든 프라미스가 완료되거나 거부된 경우에만 반환됩니다.  
  
## <a name="syntax"></a>구문  
  
```  
Promise.all(func1, func2 [,funcN])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `func1`  
 필수 요소. 프라미스를 반환하는 함수입니다.  
  
 `func2`  
 필수 요소. 프라미스를 반환하는 함수입니다.  
  
 `funcN`  
 선택 사항입니다. 프라미스를 반환하는 하나 이상의 함수입니다.  
  
## <a name="remarks"></a>설명  
 반환되는 결과는 완료된 프라미스에서 반환된 값의 배열입니다. 조인된 프라미스 중 하나가 거부되면 `Promise.all`이 프라미스 거부 이유와 함께 즉시 반환됩니다(다른 모든 반환 값은 무시됨).  
  
## <a name="example"></a>예제  
 이 코드에서 첫 번째 timeout 호출은 5000ms 후에 반환됩니다. 완료 처리기가 `Promise.all`을 호출하고, timeout 호출이 둘 다 완료되거나 거부된 경우에만 반환됩니다.  
  
```JavaScript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(resolve, duration);  
    });  
}  
  
var p = timeout(5000).then(() => {  
    return Promise.all([timeout(100), timeout(200)]);  
})  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)
---
title: "메서드 (Promise) | Microsoft Docs"
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
ms.assetid: c7f3259d-78f7-4ca7-8bdf-99fbd3f41e8d
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeb97fae19ca9923280b5099e3e4d8c839fa2815
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="then-method-promise"></a>then 메서드(Promise)
프라미스 처리 시 수행할 작업을 지정할 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
promise.then(onCompleted, onRejected);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `promise`  
 필수 요소. 프라미스 개체입니다.  
  
 `onCompleted`  
 필수 요소. 프라미스가 성공적으로 완료될 때 실행할 처리 처리기 함수입니다.  
  
 `onRejected`  
 선택 사항입니다. 프라미스가 거부될 때 실행할 오류 처리기 함수입니다.  
  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)
---
title: "Promise.reject 함수 (Promise) | Microsoft Docs"
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
ms.assetid: 9746e15b-9717-4e36-bf6b-910dcc6cd667
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0711bdd8a478d4ea07ee40ea6822af3c8c4ac610
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="promisereject-function-promise"></a>Promise.reject 함수(Promise)
전달된 인수와 동일한 결과로 거부된 새 프라미스를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
Promise.reject(r);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `r`  
 필수 요소. 프라미스가 거부된 이유입니다.  
  
## <a name="remarks"></a>설명  
 거부된 프라미스가 반환되면 `then` 또는 `catch` 메서드의 오류 처리 함수가 실행합니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
var p = Promise.reject('failure');  
p.catch(function(result) {  
    console.log(result);  
});  
  
// Output:  
// failure  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)
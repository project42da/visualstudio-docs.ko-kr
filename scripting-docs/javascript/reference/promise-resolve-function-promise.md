---
title: "Promise.resolve 함수 (Promise) | Microsoft Docs"
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
ms.assetid: 0fb6bff9-54ab-41be-97d7-04f7e6fe9cff
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6d815c9c23da48c877f7f1d995df8991429375e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="promiseresolve-function-promise"></a>Promise.resolve 함수(Promise)
결과가 해당 인수와 같은 해결된 프라미스를 새로 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
Promise.resolve(x)  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 필수 요소. 완료된 프라미스와 함께 반환되는 값입니다.  
  
## <a name="remarks"></a>설명  
 완료된 프라미스가 반환되면 `then` 메서드의 처리 함수가 실행됩니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
var p = Promise.resolve('success');  
p.then(function(result) {  
    console.log(result);  
});  
  
// Output:  
// success  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)
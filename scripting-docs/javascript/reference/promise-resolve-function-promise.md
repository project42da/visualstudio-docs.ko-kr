---
title: "Promise.resolve 함수(Promise) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 0fb6bff9-54ab-41be-97d7-04f7e6fe9cff
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# Promise.resolve 함수(Promise)
결과가 해당 인수와 같은 해결된 프라미스를 새로 만듭니다.  
  
## 구문  
  
```  
Promise.resolve(x)  
```  
  
#### 매개 변수  
 `x`  
 필수 요소.  완료된 프라미스와 함께 반환되는 값입니다.  
  
## 설명  
 완료된 프라미스가 반환되면 `then` 메서드의 처리 함수가 실행됩니다.  
  
## 예제  
  
```javascript  
var p = Promise.resolve('success');  
p.then(function(result) {  
    console.log(result);  
});  
  
// Output:  
// success  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## 참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)
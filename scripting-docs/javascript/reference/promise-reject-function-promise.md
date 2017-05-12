---
title: "Promise.reject 함수(Promise) | Microsoft Docs"
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
ms.assetid: 9746e15b-9717-4e36-bf6b-910dcc6cd667
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# Promise.reject 함수(Promise)
전달된 인수와 동일한 결과로 거부된 새 프라미스를 만듭니다.  
  
## 구문  
  
```  
Promise.reject(r);  
```  
  
#### 매개 변수  
 `r`  
 필수 요소.  프라미스가 거부된 이유입니다.  
  
## 설명  
 거부된 프라미스가 반환되면 `then` 또는 `catch` 메서드의 오류 처리 함수가 실행합니다.  
  
## 예제  
  
```javascript  
var p = Promise.reject('failure');  
p.catch(function(result) {  
    console.log(result);  
});  
  
// Output:  
// failure  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## 참고 항목  
 [Promise 개체](../../javascript/reference/promise-object-javascript.md)
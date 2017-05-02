---
title: "catch 메서드(Promise) | Microsoft Docs"
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
ms.assetid: 55266f6a-db4d-4de8-857a-8bc7d35ed4b8
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# catch 메서드(Promise)
프라미스 거부 시 수행할 작업을 지정할 수 있습니다.  
  
## 구문  
  
```  
  
promise.catch(onRejected)  
```  
  
#### 매개 변수  
 `promise`  
 필수 요소.  프라미스 개체입니다.  
  
 `onRejected`  
 필수 요소.  프라미스가 거부될 때 실행할 오류 처리기 함수입니다.  
  
## 설명  
  
## 예제  
 다음 코드 예제에서 첫 번째 timeout 호출은 5000ms 후에 반환됩니다.  이 코드에서는 프라미스가 거부되고 오류 처리기 함수가 실행됩니다.  
  
```javascript  
function timeout(duration) {  
    return new Promise(function(resolve, reject) {  
        setTimeout(reject, duration);  
    });  
}  
  
var p = timeout(5000).then(() => {  
    console.log("done!");  
}).catch(err => {  
    console.log("error!");  
})  
  
// Output (after five seconds):  
// error!  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]
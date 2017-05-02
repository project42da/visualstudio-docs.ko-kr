---
title: "codePointAt 메서드(문자열)(JavaScript) | Microsoft Docs"
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
ms.assetid: 7979018f-1be3-4a13-9e8f-c84c7ed35288
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# codePointAt 메서드(문자열)(JavaScript)
유니코드 UTF\-16 문자에 대한 코드 포인트를 반환합니다.  
  
## 구문  
  
```  
stringObj.codePointAt(pos);  
```  
  
#### 매개 변수  
 `stringObj`  
 필수.  문자열 개체입니다.  
  
 `pos`  
 필수.  문자의 위치입니다.  
  
## 설명  
 이 메서드는 모든 UTF\-16 문자에 대한 아스트랄 코드 포인트\(16 진수 값이 4 개 이상인 코드 포인트\)를 비롯한 코드 포인트 값을 반환합니다.  
  
 `pos`가 영\(0\) 보다 작거나 문자열의 크기보다 큰 경우 반환 값은 `undefined`입니다.  
  
## 예제  
 다음 예제에서는 `codePointAt` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var cp1 = "𠮷".codePointAt(0);  
vary cp2 = 'abc'.codePointAt(1);  
  
if(console && console.log) {  
    console.log(cp1);  
    console.log(cp2);}  
  
// Output:  
// 0x20BB7  
// 98  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]
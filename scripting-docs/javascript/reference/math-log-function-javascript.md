---
title: "Math.log 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "log"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "log 메서드"
  - "Math 개체"
ms.assetid: 5d617fb5-4b27-404e-842f-eea5549a7c1a
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# Math.log 함수(JavaScript)
숫자의 자연 로그\(밑 `e`\)를 반환합니다.  
  
## 구문  
  
```  
Math.log(number)   
```  
  
#### 매개 변수  
 number  
 숫자입니다.  
  
## 반환 값  
 `number`가 양수인 경우 이 함수는 숫자의 자연 로그를 반환합니다.  `number`가 음수인 경우 이 함수에서 `NaN`을 반환합니다.  `number`가 0이면 이 함수는 `-Infinity`를 반환합니다.  
  
## 예제  
 다음 예제에서는 이 함수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var numArr = [ 45.3, 69.0, 557.04, 0.222 ];  
  
for (i in numArr) {  
    document.write(Math.log(numArr[i]));  
    document.write("<br/>");  
}  
  
// Output:   
// 3.8133070324889884  
// 4.23410650459726  
// 6.322637050634291  
// -1.5050778971098575  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## 참고 항목  
 [Math.sqrt 함수](../../javascript/reference/math-sqrt-function-javascript.md)
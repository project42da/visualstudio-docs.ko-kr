---
title: "Math.acos 함수(JavaScript) | Microsoft Docs"
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
  - "acos"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "acos 메서드"
  - "arcosine 메서드"
ms.assetid: 828cb3c3-bdf7-4bb7-97ae-3617ce4b2d62
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Math.acos 함수(JavaScript)
숫자의 아크코사인\(또는 역 코사인\)을 반환합니다.  
  
## 구문  
  
```  
Math.acos(number)  
```  
  
#### 매개 변수  
 필수 `number` 인수는 숫자 식입니다.  
  
## 반환 값  
 라디안 단위의 `number` 인수의 아크코사인.  
  
## 예제  
 다음 예제에서는 `acos` 함수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var v1 = Math.acos(-1.0);  
var v2 = Math.cos(-1.0);  
  
document.write(v1);  
document.write("<br/>");  
document.write(v2);  
  
// Output:  
// 3.141592653589793  
// 0.5403023058681398  
  
```  
  
## 설명  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [Math.asin 함수](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.atan 함수](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos 함수](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin 함수](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan 함수](../../javascript/reference/math-tan-function-javascript.md)   
 [Math 개체](../../javascript/reference/math-object-javascript.md)
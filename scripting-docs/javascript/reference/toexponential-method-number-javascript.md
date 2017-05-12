---
title: "toExponential 메서드(Number)(JavaScript) | Microsoft Docs"
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
  - "toExponential"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toExponential 메서드"
ms.assetid: 7c4a6d84-3c1f-4cc4-a67d-7753e5d4ed66
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# toExponential 메서드(Number)(JavaScript)
지수 표시로 숫자를 나타냅니다.  
  
## 구문  
  
```  
  
numObj. toExponential([fractionDigits])  
```  
  
## 매개 변수  
 `numObj`  
 필수 요소.  **Number** 개체입니다.  
  
 `fractionDigits`  
 선택 사항입니다.  소수점 뒤의 자릿수입니다.  범위는 0부터 20까지여야 합니다.  
  
## 반환 값  
 숫자의 문자열 표현을 지수 표시로 반환합니다.  문자열에는 소수점 앞에 한 자리가 포함되고 소수점 뒤에 `fractionDigits`자리가 포함될 수 있습니다.  
  
 `fractionDigits`가 지정되지 않으면 `toExponential` 메서드는 숫자를 고유하게 지정하는 데 필요한 만큼 자리를 반환합니다.  
  
## 예제  
  
```javascript  
var num = new Number(123);  
var exp = num.toExponential();  
document.write(exp);  
document.write("<br/>");  
  
num = new Number(123.456);  
exp = num.toExponential(5);  
document.write(exp);  
  
// Output:   
// 1.23e+2  
// 1.23456e+2  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Number 개체](../../javascript/reference/number-object-javascript.md)  
  
## 참고 항목  
 [toFixed 메서드\(Number\)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toPrecision 메서드\(Number\)](../../javascript/reference/toprecision-method-number-javascript.md)
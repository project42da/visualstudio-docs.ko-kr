---
title: "toPrecision 메서드(Number)(JavaScript) | Microsoft Docs"
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
  - "toPrecision"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toPrecision 메서드"
ms.assetid: ac13c82f-1038-447a-823f-f755bba535ca
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# toPrecision 메서드(Number)(JavaScript)
지정된 자릿수를 사용하는 지수 표시나 고정 소수점 표시로 숫자를 나타냅니다.  
  
## 구문  
  
```  
  
numObj.toPrecision([precision])  
```  
  
## 매개 변수  
 `numObj`  
 필수 요소.  `Number` 개체입니다.  
  
 `precision`  
 선택적 요소.  유효 자릿수입니다.  범위는 1부터 21까지여야 합니다.  
  
## 반환 값  
 지수 표시로 나타낸 숫자는 소수점 뒤에 `precision` \- 1 자리가 반환되고,  고정 소수점 표시로 나타낸 숫자는 `precision` 유효 자릿수가 반환됩니다.  
  
 `precision`이 지정되지 않거나 **undefined**이면 **toString** 메서드가 대신 호출됩니다.  
  
## 예제  
 다음 코드에서는 `toPrecision`을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var num = new Number(123);  
var prec = num.toPrecision();  
document.write(prec);  
document.write("<br/>");  
  
num = new Number(123.456);  
prec = num.toPrecision(5);  
document.write(prec);  
  
// Output:  
// 123  
// 123.46  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Number 개체](../../javascript/reference/number-object-javascript.md)  
  
## 참고 항목  
 [toFixed 메서드\(Number\)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toExponential 메서드\(Number\)](../../javascript/reference/toexponential-method-number-javascript.md)
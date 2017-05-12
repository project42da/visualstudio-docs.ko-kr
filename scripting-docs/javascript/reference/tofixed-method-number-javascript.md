---
title: "toFixed 메서드(Number)(JavaScript) | Microsoft Docs"
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
  - "toFixed"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toFixed 메서드"
ms.assetid: b5f03400-865e-4ab2-818c-f734c0f6d6f0
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# toFixed 메서드(Number)(JavaScript)
고정 소수점 표시로 숫자를 나타냅니다.  
  
## 구문  
  
```  
  
numObj.toFixed([fractionDigits])  
```  
  
## 매개 변수  
 `numObj`  
 `Number` 개체가 필요합니다.  
  
 `fractionDigits`  
 선택 사항입니다.  소수점 뒤의 자릿수입니다.  범위는 0 이상 20 이하여야 합니다.  
  
## 반환 값  
 소수점 이후에 `fractionDigits` 자리를 포함하는 고정 소수점 표기법의 문자열 표현을 반환합니다.  
  
 `fractionDigits`가 지정되지 않거나 **undefined**이면 기본값이 0입니다.  
  
## 예제  
 다음 코드에서는 `toFixed`을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var num = new Number(123);  
var fix = num.toFixed();  
document.write(fix);  
document.write("<br/>");  
  
num = new Number(123.456);  
fix = num.toFixed(5);  
document.write(fix);  
  
// Output:  
// 123  
123.45600  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Number 개체](../../javascript/reference/number-object-javascript.md)  
  
## 참고 항목  
 [toExponential 메서드\(Number\)](../../javascript/reference/toexponential-method-number-javascript.md)   
 [toPrecision 메서드\(Number\)](../../javascript/reference/toprecision-method-number-javascript.md)
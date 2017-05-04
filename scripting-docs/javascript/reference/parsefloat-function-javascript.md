---
title: "parseFloat 함수(JavaScript) | Microsoft Docs"
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
  - "parseFloat"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "parseFloat 메서드"
ms.assetid: a7d87a69-1919-4623-be85-972e6376dd2d
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# parseFloat 함수(JavaScript)
문자열을 부동 소수점 숫자로 변환합니다.  
  
## 구문  
  
```  
parseFloat(numString)   
```  
  
## 설명  
 필수 `numString` 인수는 부동 소수점 숫자를 포함하는 문자열입니다.  
  
 `parseFloat` 함수는 `numString`에 포함된 숫자와 같은 숫자 값을 반환합니다.  `numString`의 접두사를 부동 소수점 숫자로 구문 분석할 수 없으면 `NaN`\(숫자 아님\)이 반환됩니다.  
  
```javascript  
parseFloat("abc")      // Returns NaN.  
parseFloat("1.2abc")   // Returns 1.2.  
```  
  
 `isNaN` 함수를 사용하면 `NaN` 여부를 테스트할 수 있습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 참고 항목  
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)   
 [parseInt 함수](../../javascript/reference/parseint-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)
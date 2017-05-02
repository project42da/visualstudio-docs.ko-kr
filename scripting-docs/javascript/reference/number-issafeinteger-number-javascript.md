---
title: "Number.isSafeInteger(Number)(JavaScript) | Microsoft Docs"
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
ms.assetid: c7ef6ce8-fe71-4e53-be44-4dd440aef21d
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# Number.isSafeInteger(Number)(JavaScript)
숫자가 JavaScript에서 안전하게 표현될 수 있는지를 나타내는 부울 값을 반환합니다.  
  
## 구문  
  
```  
Number.isSafeInteger(numValue)   
```  
  
## 반환 값  
 숫자가 `Number.MIN_SAFE_INTEGER`와 `Number.MAX_SAFE_INTEGER`\(포함\) 사이에 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## 설명  
 JavaScript에서 안전한 정수는 반올림이 적용되기 전의 IEEE\-754 배정밀도 숫자인 정수입니다.  
  
## 예제  
  
```javascript  
// Returns true  
Number.isSafeInteger(-100)  
Number.isSafeInteger(9007199254740991)  
  
// Returns false  
Number.isSafeInteger(Number.NaN)  
Number.isSafeInteger(Infinity)  
Number.isSafeInteger("100")  
Number.isSafeInteger(9007199254740992);  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [Number 개체](../../javascript/reference/number-object-javascript.md)
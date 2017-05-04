---
title: "Math.abs 함수(JavaScript) | Microsoft Docs"
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
  - "abs"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "절대값, 계산"
  - "절대 값"
  - "숫자 식"
  - "abs 메서드"
ms.assetid: 9af4b5b8-de77-47bb-bb59-abdde371e4c3
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# Math.abs 함수(JavaScript)
숫자가 양수 또는 음수인지 여부에 관계없이 숫자의 절대값을 반환합니다.  예를 들어 \-5의 절대값과 5의 절대값은 동일합니다.  
  
## 구문  
  
```  
Math.abs(number)  
```  
  
#### 매개 변수  
 필수 `number` 인수는 절대값이 필요한 숫자 식입니다.  
  
## 반환 값  
 `number` 인수의 절대값입니다.  
  
## 예제  
 다음 예제에서는 `abs` 함수의 사용법을 보여 줍니다.  
  
```javascript  
var s;  
var v1 = Math.abs(6);  
var v2 = Math.abs(-6);  
if (v1 == v2) {  
    document.write("Absolute values are the same.");  
}  
else {  
document.write("Absolute values are different.");  
}  
  
// Output: Absolute values are the same.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## 참고 항목  
 [Math 개체](../../javascript/reference/math-object-javascript.md)
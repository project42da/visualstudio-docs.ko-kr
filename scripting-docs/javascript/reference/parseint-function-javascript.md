---
title: "parseInt 함수(JavaScript) | Microsoft Docs"
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
  - "parseInt"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "parseInt 메서드"
ms.assetid: e86471af-2a0e-4359-83af-f1ac81e51421
caps.latest.revision: 24
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 24
---
# parseInt 함수(JavaScript)
문자열을 정수로 변환합니다.  
  
## 구문  
  
```  
parseInt(numString, [radix])   
```  
  
## 매개 변수  
 `numString`  
 필수 요소.  숫자로 변환할 문자열입니다.  
  
 `radix`  
 선택 사항입니다.  `numString`에서 숫자의 기수를 지정하는 2에서 36까지의 값입니다.  이 인수를 제공하지 않으면 '0x'로 시작되는 문자열은 16진수로 간주됩니다.  다른 모든 문자열은 10진수로 간주됩니다.  
  
## 설명  
 `parseInt` 함수는 `numString`에 포함된 숫자와 같은 정수 값을 반환합니다.  `numString`의 접두사를 정수로 구문 분석할 수 없으면 `NaN`\(숫자 아님\)이 반환됩니다.  
  
```javascript  
parseInt("abc");     // Returns NaN.  
parseInt("12abc");   // Returns 12.  
```  
  
 `isNaN` 함수를 사용하면 `NaN` 여부를 테스트할 수 있습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
> [!NOTE]
>  [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)]에서부터 `parseInt` 함수는 8진수로 접두사 '0'을 사용하는 문자열을 처리하지 않습니다.  그러나 `parseInt` 함수를 사용하지 않는 경우 접두사 '0'이 있는 문자열은 여전히 8진수로 해석될 수 있습니다.  8진수 정수에 대한 자세한 내용은 [데이터 형식](../../javascript/data-types-javascript.md)을 참조하십시오.  
  
## 참고 항목  
 [isNaN 함수](../../javascript/reference/isnan-function-javascript.md)   
 [parseFloat 함수](../../javascript/reference/parsefloat-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)   
 [valueOf 메서드\(Object\)](../../javascript/reference/valueof-method-object-javascript.md)
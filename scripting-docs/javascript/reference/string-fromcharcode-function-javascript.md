---
title: "String.fromCharCode 함수(JavaScript) | Microsoft Docs"
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
  - "fromCharCode"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "fromCharCodeAt 메서드"
  - "문자, 유니코드"
ms.assetid: f64120c1-23a7-48ca-8d1c-db3e8856cab4
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# String.fromCharCode 함수(JavaScript)
여러 유니코드 문자 값에서 문자열을 반환합니다.  
  
## 구문  
  
```  
String.fromCharCode([code1[, code2[, ...[, codeN]]]])   
```  
  
## 매개 변수  
 `String`  
 필수 요소.  `String` 개체입니다.  
  
 `code1`, . . . , `codeN`  
 선택 사항입니다.  문자열로 변환할 일련의 유니코드 문자 값입니다.  아무 인수도 지정되지 않으면 빈 문자열이 반환됩니다.  
  
## 설명  
 문자열 인스턴스 대신 `String` 개체에 대해 이 함수를 호출합니다.  
  
 다음 예제에서는 이 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var test = String.fromCharCode(112, 108, 97, 105, 110);  
document.write(test);  
  
// Output: plain  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [charCodeAt 메서드\(String\)](../../javascript/reference/charcodeat-method-string-javascript.md)
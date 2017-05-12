---
title: "undefined 상수(JavaScript) | Microsoft Docs"
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
  - "undefined"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "undefined 속성"
ms.assetid: 2a689d7d-00b0-48fb-9c95-5c2867bde006
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# undefined 상수(JavaScript)
초기화되지 않은 변수와 같이 정의되지 않은 값입니다.  
  
## 구문  
  
```  
undefined  
```  
  
## 설명  
 `undefined` 상수는 `Global` 개체의 멤버이고 스크립팅 엔진이 초기화되면 사용할 수 있습니다.  변수가 초기화되지 않고 선언되면 그 값은 **undefined**입니다.  
  
 변수가 선언되지 않으면 `undefined`와 비교할 수 없지만 변수 유형은 문자열 "undefined"와 비교할 수 있습니다.  
  
 `undefined` 상수는 변수를 명시적으로 테스트하거나 undefined로 설정할 경우 유용합니다.  
  
## 예제  
 다음 예제에서는 `undefined` 상수를 사용하는 방법을 보여 줍니다.  
  
```javascript  
// A variable that has not been initialized.  
var declared;  
  
if (declared == undefined)  
    document.write("declared has not been given a value <br/>");  
else  
    document.write("declared has been given a value <br/>");  
  
document.write("typeof declared is " + typeof(declared) + "<br/>");  
  
// An undeclared variable cannot be compared to undefined,  
// so the next line would generate an error.  
// if (notDeclared == undefined);  
  
document.write("typeof notDeclared is " + typeof(notDeclared));  
  
// Output:  
// declared has not been given a value  
// typeof declared is undefined  
// typeof notDeclared is undefined  
```  
  
## 요구 사항  
 `undefined` 속성은 [!INCLUDE[jsv55text](../../javascript/reference/includes/jsv55text-md.md)]에 도입되었고 [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)]에서는 읽기 전용으로 만들어졌습니다.  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 참고 항목  
 [typeof 연산자](../../javascript/reference/typeof-operator-decrementjavascript.md)
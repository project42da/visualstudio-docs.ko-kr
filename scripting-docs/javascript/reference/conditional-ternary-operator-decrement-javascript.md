---
title: "조건부(삼항) 연산자(?:)(JavaScript) | Microsoft Docs"
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
  - "?:"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "조건(삼항) 연산자"
  - "조건 연산자"
  - "삼항"
ms.assetid: 7399ac32-9324-4a9a-ae76-be9c0f9df81c
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# 조건부(삼항) 연산자(?:)(JavaScript)
조건에 따라 두 식 중 하나를 반환합니다.  
  
## 구문  
  
```  
  
test ? expression1 : expression2  
```  
  
## 매개 변수  
 `test`  
 임의의 Boolean 식입니다.  
  
 `expression1`  
 `test`가 `true`이면 식이 반환됩니다.  쉼표 식이 될 수 있습니다.  
  
 `expression2`  
 `test`가 `false`이면 식이 반환됩니다.  둘 이상의 식이 쉼표 식으로 연결될 수 있습니다.  
  
## 설명  
 `?:` 연산자는 `if...else` 문의 단축형으로 사용할 수 있으며  일반적으로 `if...else` 문을 사용하면 너무 복잡해지는 식에서 사용합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var now = new Date();  
var greeting = "Good" + ((now.getHours() > 17) ? " evening." : " day.");  
```  
  
 현재 시각이 오후 6시 이후이면 이 예제는 "Good evening."이라는 문자열을 만듭니다.  `if...else` 문을 사용하여 동일한 기능을 가진 코드를 작성하면 다음과 같습니다.  
  
```javascript  
var now = new Date();  
var greeting = "Good";  
if (now.getHours() > 17)  
   greeting += " evening.";  
else  
   greeting += " day.";  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [if...else 문](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요\(JavaScript\)](../../javascript/misc/operator-subtractsummary-javascript.md)   
 [Script Junkie 구성 위젯 샘플 응용 프로그램](http://code.msdn.microsoft.com/Script-Junkie-Configuration-543ece24)
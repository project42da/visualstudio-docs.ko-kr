---
title: "eval 함수(JavaScript) | Microsoft Docs"
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
  - "eval"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "eval 함수"
  - "구문 분석, 코드"
  - "파서"
ms.assetid: 85587e39-9325-4b75-b9f9-9d7d475a2120
caps.latest.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 21
---
# eval 함수(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드를 계산하고 실행합니다.  
  
## 구문  
  
```  
eval(codeString)   
```  
  
## 매개 변수  
 `codeString`  
 필수 요소.  올바른 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드를 포함하는 `String` 값입니다.  
  
## 설명  
 `eval` 함수를 사용하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 소스 코드를 동적으로 실행할 수 있습니다.  
  
 `codeString` 문자열은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 파서에 의해 구문 분석되고 실행됩니다.  
  
 `eval` 함수에 전달된 코드는 `eval` 함수가 호출되는 것과 같은 상황에서 실행됩니다.  
  
 가능한 모든 경우에 [JSON.parse 함수](../../javascript/reference/json-parse-function-javascript.md)를 사용하여 JSON\(JavaScript Object Notation\) 텍스트를 deserialize하세요.  `JSON.parse` 함수는 `eval` 함수보다 안전하고 실행 속도도 빠릅니다.  
  
## 예제  
 다음 코드에서는 변수 `myDate`를 테스트 날짜로 초기화합니다.  
  
```javascript  
var dateFn = "Date(1971,3,8)";  
var myDate;  
eval("myDate = new " + dateFn + ";");  
  
document.write(myDate);  
  
// Output: Thu Apr 8 00:00:00 PDT 1971  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)
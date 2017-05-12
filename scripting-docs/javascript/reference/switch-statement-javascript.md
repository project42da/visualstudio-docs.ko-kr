---
title: "switch 문(JavaScript) | Microsoft Docs"
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
  - "switch_JavaScriptKeyword"
  - "default_JavaScriptKeyword"
  - "case_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "switch 문"
ms.assetid: 61f80e8b-3739-4146-a893-c2832d92b28c
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# switch 문(JavaScript)
지정한 식의 값이 레이블과 일치하면 하나 이상의 문을 실행하도록 합니다.  
  
## 구문  
  
```  
switch (expression) {  
    case label :  
        statementlist  
    case label :  
    default :  
        statementlist  
}   
```  
  
## 매개 변수  
 `expression`  
 계산할 식입니다.  
  
 `label`  
 `expression`과 일치하는 식별자입니다.  `label`이 `expression`인 경우 콜론 바로 다음의 `statementlist`에서 실행이 시작되고 선택 사항인 `break` 문에 도달할 때까지 또는 `switch` 문의 끝까지 계속 실행됩니다.  
  
 `statementlist`  
 실행할 하나 이상의 문입니다.  
  
## 설명  
 `default` 절을 사용하면 `expression`과 일치하는 레이블 값이 없을 경우 실행할 문을 제공할 수 있습니다.  이 절은 `switch` 코드 블록 내의 어디에나 올 수 있습니다.  
  
 `label` 블록은 0개 이상 지정할 수 있습니다.  `expression` 값과 일치하는 `label`이 없고 `default` 사례가 제공되지 않은 경우 문이 실행되지 않습니다.  
  
 `switch` 문은 다음과 같이 실행됩니다.  
  
-   일치하는 것을 찾을 때까지 `expression`을 계산한 후 `label`을 살펴봅니다.  
  
-   `label` 값이 `expression`과 같으면 해당 `statementlist`를 실행합니다.  
  
     `break` 문을 만나거나 `switch` 문이 끝날 때까지 실행을 계속합니다.  따라서 `break` 문을 사용하지 않으면 여러 `label` 블록이 실행됩니다.  
  
-   `expression`과 일치하는 `label`이 없으면 `default` 사례로 이동합니다.  `default` 사례도 없으면 마지막 단계로 이동합니다.  
  
-   `switch` 코드 블록의 끝 다음에 나오는 문을 계속 실행합니다.  
  
## 예제  
 다음 예제에서는 개체 형식을 테스트합니다.  
  
```javascript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
            break;  
        case Number:  
            document.write("Object is a Number.");  
            break;  
        case String:  
            document.write("Object is a String.");  
            break;  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.  
  
// Output when obj is a Number:  
// Object is a Number.  
  
// Output when obj is a String:  
// Object is a String.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## 예제  
 다음 코드에서는 `break` 문을 사용하지 않을 경우의 동작을 보여 줍니다.  
  
```javascript  
function MyObjectType(obj) {  
    switch (obj.constructor) {  
        case Date:  
            document.write("Object is a Date.");  
        case Number:  
            document.write("Object is a Number.");  
        case String:  
            document.write("Object is a String.");  
        default:  
            document.write("Object is unknown.");  
    }  
}  
  
// Output when obj is a Date:  
// Object is a Date.Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a Number:  
// Object is a Number.Object is a String.Object is unknown.  
  
// Output when obj is a String:  
// Object is a String.Object is unknown.  
  
// Output when obj is something other than a Date, Number, or String:  
// Object is unknown.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## 참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [if...else 문](../../javascript/reference/if-dot-dot-dot-else-statement-javascript.md)
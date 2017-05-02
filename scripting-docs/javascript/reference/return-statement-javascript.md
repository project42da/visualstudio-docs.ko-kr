---
title: "return 문(JavaScript) | Microsoft Docs"
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
  - "return_JavaScriptKeyword"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "function 문"
  - "return 문"
  - "return 문, 스크립트에서 함수 종료"
  - "return 문, 구문"
  - "실행 종료"
ms.assetid: a9130d90-11fb-43f5-a819-7e5435f74c05
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# return 문(JavaScript)
현재 함수를 종료하고 그 함수로부터 값을 반환합니다.  
  
## 구문  
  
```  
  
return[(][expression][)];   
```  
  
## 설명  
 선택적인 *expression* 인수는 함수로부터 반환할 값입니다.  생략하면 함수는 값을 반환하지 않습니다.  
  
 `return` 문을 사용하면 함수 실행을 중지하고 *expression* 값을 반환할 수 있습니다.  *expression*을 생략하거나 함수 내에서 `return` 문이 실행되지 않으면 현재 함수를 호출한 식에 undefined 값이 할당됩니다.  
  
## 예제  
 다음 예제는 `return` 문의 사용 예를 보여 줍니다.  
  
```javascript  
function myfunction(arg1, arg2){  
   var r;  
   r = arg1 * arg2;  
   return(r);  
}  
```  
  
## 예제  
 다음 예제에서는 `return` 문을 사용하여 함수를 반환하는 방법을 보여 줍니다.  
  
```javascript  
function doWork() {  
    return function calculate(y) { return y + 1; };  
}  
  
var func = doWork();  
var x = func(5);  
document.write(x);  
  
// Output: 6  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)
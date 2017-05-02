---
title: "Function 개체(JavaScript) | Microsoft Docs"
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
  - "function"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Function 개체"
ms.assetid: d3834767-203c-475e-848c-95c423ba15b6
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# Function 개체(JavaScript)
새 함수를 만듭니다.  
  
## 구문  
  
```  
function functionName([argname1  [, ...[, argnameN]]])  
{  
   body  
}  
```  
  
## 구문  
  
```  
  
functionName = new Function( [argname1,  [... argnameN,]] body );  
```  
  
## 매개 변수  
 `functionName`  
 필수 요소.  새로 만든 함수의 이름입니다.  
  
 `argname1...argnameN`  
 선택 사항입니다.  함수가 수락하는 인수 목록입니다.  
  
 `body`  
 선택 사항입니다.  함수를 호출하면 실행되는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 코드 블록이 들어 있는 문자열입니다.  
  
## 설명  
 함수는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 기본 데이터 형식입니다.  구문 1은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 필요한 경우 `Function` 개체로 변환하는 함수 값을 만듭니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 함수를 호출할 때 구문 2에서 만든 `Function` 개체를 함수 값으로 변환합니다.  
  
 구문 1은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 새 함수를 만드는 표준 방법입니다.  구문 2는 명시적으로 함수 개체를 만드는 데 사용되는 대체 형식입니다.  
  
 예를 들어 함수에 전달된 두 인수를 추가하는 함수를 선언하려면 다음 두 가지 방법 중 하나로 선언하면 됩니다.  
  
## 예제 1  
  
```javascript  
function add(x, y)  
{  
   return(x + y);  
}  
```  
  
## 예제 2  
  
```  
var add = function(x, y) {  
     return(x+y);  
}  
```  
  
 두 경우 중 하나에서 다음과 비슷한 코드 줄을 사용하여 함수를 호출합니다.  
  
```javascript  
add(2, 3);  
```  
  
> [!NOTE]
>  함수를 호출할 때는 괄호와 모든 필수 인수를 항상 포함해야 합니다.  괄호 없이 함수를 호출하면 함수의 반환 값 대신 함수 자체가 반환됩니다.  
  
## 속성  
 [0...  
          n 속성](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md) &#124;[arguments 속성](../../javascript/reference/arguments-property-function-javascript.md) &#124; [callee 속성](../../javascript/reference/callee-property-arguments-javascript.md) &#124; [caller 속성](../../javascript/reference/caller-property-function-javascript.md) &#124; [constructor 속성](../../javascript/reference/constructor-property-object-javascript.md) &#124; [length 속성\(Function\)](../../javascript/reference/length-property-function-javascript.md) &#124; [prototype 속성](../../javascript/reference/prototype-property-object-javascript.md)  
  
## 메서드  
 [apply 메서드](../../javascript/reference/apply-method-function-javascript.md) &#124; [bind 메서드](../../javascript/reference/bind-method-function-javascript.md) &#124; [call 메서드](../../javascript/reference/call-method-function-javascript.md) &#124; [toString 메서드](../../javascript/reference/tostring-method-object-javascript.md) &#124; [valueOf 메서드](../../javascript/reference/valueof-method-object-javascript.md)  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## 참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [var 문](../../javascript/reference/var-statement-javascript.md)
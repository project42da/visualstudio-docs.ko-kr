---
title: "변수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "대/소문자 구분, JavaScript 변수 이름"
  - "강제"
ms.assetid: 12a450e5-4818-4a09-9878-cd7c6cd2a248
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# 변수(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 변수에 "hello" 또는 5와 같은 값이 포함됩니다.  변수를 사용할 때 변수가 나타내는 데이터를 참조합니다\(예: `NumberOfDaysLeft = EndDate – TodaysDate`\).  
  
 코드에 표시되는 값을 저장, 검색 및 조작하는 데 변수를 사용합니다.  다른 사용자가 코드가 수행하는 작업을 쉽게 이해할 수 있도록 변수에 의미를 알 수 있는 이름을 지정합니다.  
  
## 변수 선언  
 선언은 스크립트에 변수가 처음 표시되는 경우입니다.  변수를 처음 언급하면 메모리에 변수가 설정되어 나중에 스크립트에서 참조할 수 있습니다.  변수는 항상 선언한 후 사용해야 합니다.  `var` 키워드를 사용하여 이 작업을 수행합니다.  
  
```javascript  
// A single declaration.  
var count;    
// Multiple declarations with a single var keyword.  
var count, amount, level;      
// Variable declaration and initialization in one statement.  
var count = 0, amount = 100;   
```  
  
 `var` 문에서 변수를 초기화하지 않으면 변수가 `undefined` 값을 자동으로 수행합니다.  
  
## 변수 이름 지정  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 대\/소문자를 구분하는 언어입니다.  즉, myCounter와 같은 변수 이름은 변수 이름 MYCounter와 다릅니다.  변수 이름의 길이는 임의로 지정할 수 있습니다.  올바른 변수 이름을 만드는 규칙은 다음과 같습니다.  
  
-   첫 번째 문자는 ASCII 문자\(대문자 또는 소문자\)이거나 밑줄\(\_\) 문자여야 합니다.  첫 번째 문자에는 숫자를 사용할 수 없습니다.  
  
-   그 다음 문자는 문자, 숫자 또는 밑줄\(\_\)이어야 합니다.  
  
-   [예약어](../javascript/reference/javascript-reserved-words.md)는 변수 이름으로 사용할 수 없습니다.  
  
 다음은 올바른 변수 이름의 예입니다.  
  
```  
_pagecount   
Part9   
Number_Items   
```  
  
 다음은 잘못된 변수 이름의 예입니다.  
  
```javascript  
// Cannot begin with a number.   
99Balloons     
// The ampersand (&) character is not a valid character for variable names.   
Alpha&Beta   
```  
  
 변수를 선언하고 초기화하지만 특정 값을 지정하지 않으려는 경우 변수에 `null` 값을 할당합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var bestAge = null;  
var muchTooOld = 3 * bestAge; // muchTooOld has the value 0.  
```  
  
 값을 할당하지 않고 변수를 선언하면 변수가 `undefined` 값을 갖게 됩니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var currentCount;  
// finalCount has the value NaN because currentCount is undefined.  
var finalCount = 1 * currentCount;   
```  
  
 `null` 값은 숫자 0과 같이 동작하며 `undefined`는 특수 값 `NaN`\(숫자가 아님\)처럼 동작합니다.  `null` 값을 `undefined` 값과 비교하는 경우 두 값은 동일합니다.  
  
 선언에 `var` 키워드를 사용하지 않고 변수를 선언한 다음 변수에 값을 할당할 수 있습니다.  이는 암시적 선언입니다.  
  
```javascript  
// The variable noStringAtAll is declared implicitly.  
noStringAtAll = "";   
```  
  
 선언하지 않은 변수는 사용할 수 없습니다.  
  
```javascript  
// Error. Length and width do not yet exist.  
var area = length * width;   
```  
  
## 강제 변환  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 자유로운 형식의 언어로 엄격한 형식의 언어인 C\+\+과 반대됩니다.  즉, JavaScript 변수에는 미리 정의된 형식이 없습니다.  대신, 변수 형식은 값의 형식입니다.  이 동작을 통해 값을 다른 형식인 것처럼 처리할 수 있습니다.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 예외를 발생시키지 않고 서로 다른 형식의 값에 대한 작업을 수행할 수 있습니다.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 해석기는 한 데이터 형식에서 다른 데이터 형식으로 암묵적으로 변환하거나 *강제 변환*한 후 연산을 수행합니다.  문자열, 숫자 및 부울 값을 강제 변환하는 규칙은 다음과 같습니다.  
  
-   숫자 및 문자열을 추가하면 숫자가 문자열로 강제 변환됩니다.  
  
-   부울 및 문자열을 추가하면 부울이 문자열로 강제 변환됩니다.  
  
-   숫자 및 부울을 추가하면 부울이 숫자로 강제 변환됩니다.  
  
 다음 예에서는 문자열에 추가된 숫자가 문자열이 됩니다.  
  
```javascript  
var x = 2000;  
var y = "Hello";  
// The number is coerced to a string.  
x = x + y;  
document.write(x);   
  
// Output:  
// 2000Hello  
```  
  
 문자열은 비교를 위해 해당 숫자로 자동으로 변환됩니다.  문자열을 정수로 명시적으로 변환하려면 [parseInt 함수](../javascript/reference/parseint-function-javascript.md)를 사용합니다.  문자열을 숫자로 명시적으로 변환하려면 [parseFloat 함수](../javascript/reference/parsefloat-function-javascript.md)를 사용합니다.
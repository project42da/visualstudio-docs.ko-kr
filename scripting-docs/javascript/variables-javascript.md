---
title: 변수(JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- coercion
- case sensitivity, JavaScript variable name
ms.assetid: 12a450e5-4818-4a09-9878-cd7c6cd2a248
caps.latest.revision: 20
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c1d09f634bd4901e4015766bf55f272926a0a31c
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="variables-javascript"></a>변수(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 변수에는 “hello” 또는 5라는 값이 포함됩니다. 변수를 사용하면 해당 변수가 나타내는 데이터를 참조합니다(예; `NumberOfDaysLeft = EndDate - TodaysDate`).  
  
 변수를 사용하여 코드에 표시되는 값을 저장, 검색 및 조작합니다. 다른 사용자가 코드를 통해 수행하는 작업을 이해하기 쉽도록 변수에 의미 있는 이름을 지정하세요.  
  
## <a name="declaring-variables"></a>변수 선언  
 스크립트에 변수를 선언할 때 변수가 처음 표시됩니다. 변수를 처음 언급할 때 메모리에 설정되므로 스크립트에서 나중에 참조할 수 있습니다. 사용하기 전에 변수를 선언해야 합니다. `var` 키워드를 사용하여 이 작업을 수행합니다.  
  
```JavaScript  
// A single declaration.  
var count;    
// Multiple declarations with a single var keyword.  
var count, amount, level;      
// Variable declaration and initialization in one statement.  
var count = 0, amount = 100;   
```  
  
 `var` 문에서 변수를 초기화하지 않으면 자동으로 `undefined`를 사용합니다.  
  
## <a name="naming-variables"></a>변수 이름 지정  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 대소문자를 구분하는 언어입니다. 즉, **myCounter**와 같은 변수 이름은 변수 이름 **MYCounter**와 다릅니다. 변수 이름의 길이는 다음과 같을 수 있습니다. 유효한 변수 이름을 만드는 규칙은 다음과 같습니다.  
  
-   첫 번째 문자는 ASCII 문자(대문자 또는 소문자), 유니코드 변수 명명 규칙을 준수하는 문자 또는 밑줄 친(_) 문자여야 합니다. 숫자는 첫 번째 문자로 사용할 수 없습니다.  
  
-   후속 문자는 문자, 숫자 또는 밑줄(_)이어야 합니다.  
  
-   변수 이름은 [예약어](../javascript/reference/javascript-reserved-words.md)가 아니어야 합니다.  
  
 유효한 변수 이름의 예는 다음과 같습니다.  
  
```  
_pagecount   
Part9   
Number_Items   
```  
  
 유효하지 않은 변수 이름의 예는 다음과 같습니다.  
  
```JavaScript  
// Cannot begin with a number.   
99Balloons     
// The ampersand (&) character is not a valid character for variable names.   
Alpha&Beta   
```  
  
 변수를 선언하고 초기화하지만 특정 값은 제공하지 않으려는 경우 `null` 값을 할당합니다. 예를 들면 다음과 같습니다.  
  
```JavaScript  
var bestAge = null;  
var muchTooOld = 3 * bestAge; // muchTooOld has the value 0.  
```  
  
 값을 할당하지 않고 변수를 선언하면 값이 `undefined`가 됩니다. 예를 들면 다음과 같습니다.  
  
```JavaScript  
var currentCount;  
// finalCount has the value NaN because currentCount is undefined.  
var finalCount = 1 * currentCount;   
```  
  
 `null` 값은 숫자 0과 같이 동작하는 반면 `undefined`는 특수 값 `NaN`(숫자가 아님)과 같이 동작합니다. `null` 값과 `undefined` 값을 비교하자면 이 두 값은 동일합니다.  
  
 선언에서 `var` 키워드를 사용하지 않고 변수를 선언하고 값을 할당할 수 있습니다. 이는 암시적 선언입니다.  
  
```JavaScript  
// The variable noStringAtAll is declared implicitly.  
noStringAtAll = "";   
```  
  
 선언되지 않은 변수는 사용할 수 없습니다.  
  
```JavaScript  
// Error. Length and width do not yet exist.  
var area = length * width;   
```  
  
## <a name="coercion"></a>강제 변환  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 C++와 같은 강력한 형식의 언어와 반대로 느슨하게 형식화된 언어입니다. 즉, JavaScript 변수에 미리 결정된 형식이 없습니다. 대신, 변수 유형 값이 해당 값의 형식입니다. 이 동작을 사용하면 다른 유형인 것처럼 값을 처리할 수 있습니다.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 예외를 발생시키지 않고 다른 유형의 값에 대해 작업을 수행할 수 있습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 인터프리터에서 데이터 형식 중 하나를 다른 형식으로 내재적으로 변환하거나 *강제 변환*한 다음 작업을 수행합니다. 문자열, 숫자 및 부울 값을 강제 변환하는 규칙은 다음과 같습니다.  
  
-   숫자와 문자열을 추가한 경우 숫자는 문자열로 강제 변환됩니다.  
  
-   부울과 문자열을 추가한 경우 부울은 문자열로 강제 변환됩니다.  
  
-   숫자와 부울을 추가한 경우 부울은 숫자로 강제 변환됩니다.  
  
 다음 예제에서는 문자열에 추가된 숫자가 결과적으로 문자열이 됩니다.  
  
```JavaScript  
var x = 2000;  
var y = "Hello";  
// The number is coerced to a string.  
x = x + y;  
document.write(x);   
  
// Output:  
// 2000Hello  
```  
  
 비교를 위해 문자열이 해당 숫자로 자동 변환됩니다. 명시적으로 문자열을 정수로 변환하려면 [parseInt 함수](../javascript/reference/parseint-function-javascript.md)를 사용합니다. 명시적으로 문자열을 숫자로 변환하려면 [parseFloat 함수](../javascript/reference/parsefloat-function-javascript.md)를 사용합니다.
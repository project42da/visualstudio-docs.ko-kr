---
title: JavaScript 코드 작성 | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- vs.htmldesigner.html
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- code, JavaScript syntax
- comments, JavaScript code
- JavaScript code
ms.assetid: dde28266-0d0f-4460-a819-f931cf0911ad
caps.latest.revision: 19
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e50bc25f818724b59d9adda51f97d76ae14de2b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="writing-javascript-code"></a>JavaScript 코드 작성
다른 많은 프로그래밍 언어와 마찬가지로 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 명령문, 관련 명령문 집합으로 구성된 블록 및 주석으로 구성됩니다. 명령문 내에서 변수, 문자열, 숫자 및 식을 사용할 수 있습니다.  
  
## <a name="statements"></a>문  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 프로그램은 여러 명령문의 모음입니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문은 하나의 완전한 작업을 수행하는 방식으로 표현을 결합합니다.  
  
 명령문은 하나 이상의 식, 키워드 또는 연산자(기호)로 구성됩니다. 일반적으로 명령문은 한 줄로 작성되지만, 두 줄 이상으로 작성될 수도 있습니다. 또한 둘 이상의 명령문을 세미콜론으로 분리하여 같은 줄에 작성할 수 있습니다. 일반적으로 새로운 각 줄에서 새 명령문을 시작합니다. 명령문은 명시적으로 종료하는 것이 좋습니다. 이렇게 하려면 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 명령문 종료 문자인 세미콜론(;)을 사용합니다.  
  
 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 명령문의 두 가지 예제입니다. // 문자 뒤의 문장은 *주석*이며, 이는 프로그램에서 설명 주석이 됩니다.  
  
```JavaScript  
var aBird = "Robin"; // Assign the text "Robin" to the variable aBird.  
var today = new Date(); // Assign today's date to the variable today.  
```  
  
 중괄호({})로 묶은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 명령문 그룹을 *블록*이라고 합니다. 블록으로 그룹화된 명령문은 일반적으로 단일 명령문으로 처리할 수 있습니다. 즉 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 단일 명령문을 기대하는 대부분의 위치에서 블록을 사용할 수 있습니다. 주목할 만한 예외에는 **for** 및 `while` 루프에 대한 헤더가 포함됩니다. 블록 내의 단일 명령문은 세미콜론으로 끝나지만, 블록 자체는 끝나지 않습니다.  
  
 블록은 일반적으로 함수와 조건문에 사용됩니다. C++ 및 일부 다른 언어와 달리 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 블록을 새 범위로 고려하지 않습니다. 함수만 새 범위를 만듭니다.  
  
 다음 예제에서 `else` 절에는 중괄호로 묶은 두 개의 명령문 블록이 포함되어 있습니다. 블록은 단일 명령문으로 처리됩니다. 또한 함수 자체는 중괄호로 묶은 명령문 블록으로 구성됩니다. 함수 아래의 명령문은 블록 외부에 있으므로 함수 정의의 일부가 아닙니다.  
  
```JavaScript  
function inchestometers(inches)  
   {  
   if (inches < 0)  
      return -1;  
   else  
      {  
      var meters = inches / 39.37;  
      return meters;  
      }  
   }  
  
var inches = 12;  
var meters = inchestometers(inches);  
document.write("the value in meters is " + meters);  
```  
  
## <a name="comments"></a>설명  
 한 줄 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 주석은 쌍 슬래시(//)로 시작합니다. 다음은 한 줄 주석의 예제입니다.  
  
```JavaScript  
var aGoodIdea = "Comment your code thoroughly."; // This is a single-line comment.  
```  
  
 여러 줄 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 주석은 슬래시와 별표(/\*)로 시작하고 이와 반대로(\*/) 끝납니다.  
  
```JavaScript  
/*  
This is a multiline comment that explains the preceding code statement.  
  
The statement assigns a value to the aGoodIdea variable. The value,   
which is contained between the quote marks, is called a literal. A   
literal explicitly and directly contains information; it does not   
refer to the information indirectly. The quote marks are not part   
of the literal.  
*/  
```  
  
> [!NOTE]
>  여러 줄 주석을 다른 줄에 포함하려는 경우 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 결과적인 여러 줄 주석을 예기치 않은 방식으로 해석합니다. 포함된 여러 줄 주석의 끝을 표시하는 */는 전체 여러 줄 주석의 끝으로 해석됩니다. 즉 포함된 여러 줄 주석 뒤에 오는 텍스트는 주석 처리되지 않습니다. 대신 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드로 해석되어 구문 오류가 발생합니다.  
  
 모든 주석은 한 줄 주석 블록으로 작성하는 것이 좋습니다. 이렇게 하면 나중에 코드의 큰 부분을 여러 줄 주석으로 주석 처리할 수 있습니다.  
  
```JavaScript  
// This is another multiline comment, written as a series of single-line comments.  
// After the statement is executed, you can refer to the content of the   
// aGoodIdea variable by using its name.  
var extendedIdea = aGoodIdea + " You never know when you'll have to figure out what it does.";  
```  
  
## <a name="assignments-and-equality"></a>할당 및 같음  
 등호(=)는 할당 연산자로서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 명령문에서 값을 변수에 할당하는 데 사용됩니다. = 연산자의 왼쪽 피연산자는 항상 Lvalue입니다. Lvalues의 예는 다음과 같습니다.  
  
-   변수,  
  
-   배열 요소,  
  
-   개체 속성  
  
 = 연산자의 오른쪽 피연산자는 항상 Rvalue입니다. Rvalues는 식의 값을 포함하여 모든 형식의 임의 값이 될 수 있습니다. 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 할당 명령문 예제입니다.  
  
```JavaScript  
var anInteger = 3;  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 컴파일러는 이 명령문을 "**anInteger** 변수에 값 3을 할당합니다." 또는 "**anInteger**에서 값 3을 사용합니다."로 해석합니다.  
  
 = 연산자(할당)와 == 연산자(같음)의 차이점을 이해해야 합니다. 두 값을 비교하여 같은지 확인하려면 두 개의 등호(==)를 사용합니다. 이에 대해서는 [프로그램 흐름 제어](../javascript/controlling-program-flow-javascript.md)에서 자세히 설명합니다.  
  
## <a name="expressions"></a>식  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 식의 값은 유효한 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 형식(숫자, 문자열, 개체 등)일 수 있습니다. 가장 간단한 식은 리터럴입니다. 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 리터럴 식의 몇 가지 예제입니다.  
  
```JavaScript  
3.9                       // numeric literal  
"Hello!"                  // string literal  
false                     // boolean literal  
null                      // literal null value  
{x:1, y:2}                // Object literal  
[1,2,3]                   // Array literal  
function(x){return x*x;}  // function literal  
```  
  
 더 복잡한 식에는 변수, 함수 호출 및 기타 식이 포함될 수 있습니다. 복합 식을 만들기 위해 연산자를 사용하여 식을 결합할 수 있습니다. 연산자의 예로 `+`(더하기), `-`(빼기), `*`(곱하기) 및 `/`(나누기)가 있습니다.  
  
 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 복합 식의 몇 가지 예제입니다.  
  
```JavaScript  
var anExpression = 3 * (4 / 5) + 6;  
var aSecondExpression = Math.PI * radius * radius;  
var aThirdExpression = aSecondExpression + "%" + anExpression;  
var aFourthExpression = "(" + aSecondExpression + ") % (" + anExpression + ")";  
```
---
title: "JavaScript 코드 작성 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.htmldesigner.html"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "코드, JavaScript 구문"
  - "주석, JavaScript 코드"
  - "JavaScript 코드"
ms.assetid: dde28266-0d0f-4460-a819-f931cf0911ad
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# JavaScript 코드 작성
다른 많은 프로그래밍 언어와 마찬가지로, [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 문, 관련 문 집합으로 구성된 블록 및 주석으로 이루어져 있습니다.  문 내부에는 변수, 문자열, 숫자 및 식을 사용할 수 있습니다.  
  
## 문  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 프로그램은 여러 문의 컬렉션입니다.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문은 하나의 전체 작업을 수행하는 방식으로 식을 결합합니다.  
  
 문은 한 개 이상의 식, 키워드 또는 연산자\(기호\)로 구성됩니다.  일반적으로 한 개의 문은 한 줄로 작성되지만, 둘 이상의 줄에 작성될 수도 있습니다.  또한 세미콜론으로 구분하여 같은 줄에 둘 이상의 문을 작성할 수 있습니다.  일반적으로 새 줄에서 각각 새로운 문이 시작됩니다.  명시적으로 문을 종결하는 것이 좋습니다.  이렇게 하려면 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문 종결 문자인 세미콜론\(;\)을 사용합니다.  
  
 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문을 사용한 두 가지 예제입니다.  \/\/ 문자 뒤의 문장은 프로그램의 참고 설명인 *주석*입니다.  
  
```javascript  
var aBird = "Robin"; // Assign the text "Robin" to the variable aBird.  
var today = new Date(); // Assign today's date to the variable today.  
```  
  
 중괄호\({}\)로 둘러싸인 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문의 그룹을 *블록*이라고 합니다.  한 블록에 그룹화된 여러 문은 일반적으로 단일 문으로 처리할 수 있습니다.  따라서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 단일 문이 필요한 대부분의 위치에 블록을 사용할 수 있습니다.  **for** 및 `while` 루프의 헤더는 예외적인 경우입니다.  블록 내의 단일 문은 세미콜론으로 끝나지만 블록 자체는 세미콜론으로 끝나지 않습니다.  
  
 일반적으로 블록은 함수와 조건부에서 사용됩니다.  C\+\+ 및 다른 일부 언어와는 달리 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 블록을 새 범위로 처리하지 않으며 함수에서만 새로운 범위를 만듭니다.  
  
 다음 예제에서 `else` 절에는 중괄호로 둘러싸인 두 개의 문 블록이 포함되어 있습니다.  블록은 단일 문으로 처리됩니다.  또한 함수 자체는 중괄호로 둘러싸인 문 블록으로 구성됩니다.  함수 아래의 문은 블록 외부에 있으므로 함수 정의에 포함되지 않습니다.  
  
```javascript  
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
  
## 주석  
 한 줄로 된 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 주석은 슬래시 두 개\(\/\/\)로 시작합니다.  다음은 한 줄로 된 주석의 예제입니다.  
  
```javascript  
var aGoodIdea = "Comment your code thoroughly."; // This is a single-line comment.  
```  
  
 여러 줄로 된 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 주석은 슬래시와 별표\(\/\*\)로 시작하고 별표와 슬래시\(\*\/\)로 끝납니다.  
  
```javascript  
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
>  여러 줄로 된 주석을 여러 줄로 된 다른 주석에 포함시키려고 하면 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 여러 줄로 된 주석이 예상치 못한 방식으로 해석됩니다.  여러 줄로 된 포함 주석의 끝을 표시하는 \*\/는 여러 줄로 된 주석 전체의 끝으로 해석됩니다.  따라서 여러 줄로 된 포함 주석 다음에 나오는 텍스트는 주석 처리되지 않고 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드로 해석되어 구문 오류가 발생합니다.  
  
 모든 주석은 한 줄로 된 주석 블록으로 작성하는 것이 좋습니다.  이렇게 하면 나중에 큰 세그먼트의 코드를 여러 줄로 된 주석으로 처리할 수 있습니다.  
  
```javascript  
// This is another multiline comment, written as a series of single-line comments.  
// After the statement is executed, you can refer to the content of the   
// aGoodIdea variable by using its name.  
var extendedIdea = aGoodIdea + " You never know when you'll have to figure out what it does.";  
```  
  
## 할당 및 같음  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문에서 등호\(\=\)는 변수에 값을 할당하는데 사용되며 할당 연산자라고 합니다.  \= 연산자의 왼쪽 피연산자는 항상 Lvalue입니다.  Lvalue의 예는 다음과 같습니다.  
  
-   변수  
  
-   배열 요소  
  
-   개체 속성  
  
 \= 연산자의 오른쪽 피연산자는 항상 Rvalue입니다.  Rvalue는 식의 값을 포함하여 모든 형식의 임의 값일 수 있습니다.  다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 할당 문의 예제입니다.  
  
```javascript  
var anInteger = 3;  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 컴파일러는 이 문을 "**anInteger** 변수에 값 3 할당" 또는 "**anInteger**에 값 3 사용"으로 해석합니다.  
  
 \= 연산자\(할당\) 및 \=\= 연산자\(같음\)의 차이점을 확실히 알아야 합니다.  두 값을 비교하여 같은지 확인하려는 경우 두 개의 등호\(\=\=\)를 사용합니다.  이 내용은 [프로그램 흐름 제어](../javascript/controlling-program-flow-javascript.md)에서 자세히 설명합니다.  
  
## 식  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 식 값은 숫자, 문자열, 개체 등 유효한 모든 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 형식일 수 있습니다.  가장 간단한 식을 리터럴이라고 합니다.  다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 리터럴 식의 예제입니다.  
  
```javascript  
3.9                       // numeric literal  
"Hello!"                  // string literal  
false                     // boolean literal  
null                      // literal null value  
{x:1, y:2}                // Object literal  
[1,2,3]                   // Array literal  
function(x){return x*x;}  // function literal  
```  
  
 좀더 복잡한 식은 변수, 함수 호출 및 다른 식을 포함할 수 있습니다.  연산자로 식을 결합하여 복잡한 식을 만들 수 있습니다.  연산자의 예에는 `+`\(더하기\), `-`\(빼기\), `*`\(곱하기\) 및 `/`\(나누기\)가 있습니다.  
  
 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 복합 식의 예제입니다.  
  
```javascript  
var anExpression = 3 * (4 / 5) + 6;  
var aSecondExpression = Math.PI * radius * radius;  
var aThirdExpression = aSecondExpression + "%" + anExpression;  
var aFourthExpression = "(" + aSecondExpression + ") % (" + anExpression + ")";  
```
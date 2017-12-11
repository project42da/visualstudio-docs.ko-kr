---
title: "프로그램 흐름 제어(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Boolean values, program flow
- continue statement
- break statement
- control flow, about control flow
ms.assetid: 4ef58c82-e5d6-4b09-9458-cf0aa3b39bf5
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 20c256d26c6991067d7c25c0c835eda6e5e5aac6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="controlling-program-flow-javascript"></a>프로그램 흐름 제어(JavaScript)
일반적으로 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 스크립트의 문들은 작성된 순서대로 하나씩 실행됩니다. 이는 순차적 실행이라고 하며 프로그램 흐름의 기본 방향입니다.  
  
 순차적 실행 외에 프로그램 흐름이 스크립트의 다른 부분으로 이동되는 방법이 있습니다. 즉, 순차적으로 다음 문을 실행하는 대신 다른 문이 실행됩니다.  
  
 스크립트 활용도를 높이려면 이러한 제어 이동을 논리적 방식으로 수행해야 합니다. 프로그램 제어는 부울 **true** 또는 **false**를 반환하는 명제 문의 결과에 따라 이동됩니다. 식을 만든 다음 그 결과가 true인지 테스트합니다. 이를 수행하기 위한 프로그램 구조는 크게 두 가지 종류입니다.  
  
 첫 번째는 선택 구조입니다. 선택 구조를 사용하면 도로의 갈림길과 같이 프로그램의 교차점을 만들어 프로그램 흐름을 선택할 수 있습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 사용할 수 있는 선택 구조는 다음 네 가지입니다.  
  
-   단일 선택 구조(**if**),  
  
-   이중 선택 구조(**if/else**),  
  
-   인라인 삼항 연산자 `?:`  
  
-   다중 선택 구조(`switch`)  
  
 프로그램 제어 구조의 두 번째 형식은 반복 구조입니다. 이 구조를 사용하면 일부 조건이 true로 남아 있는 한 작업을 반복하도록 지정할 수 있습니다. 제어문의 조건이 만족되면(보통 특정 수만큼 반복된 후) 제어는 반복 구조를 떠나 다음 문으로 전달됩니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 사용할 수 있는 반복 구조는 다음 네 가지입니다.  
  
-   루프 위쪽에서 식 테스트(`while`)  
  
-   루프 아래쪽에서 식 테스트(**do/while**),  
  
-   개체의 각 속성에 대한 연산(**for/in**).  
  
-   카운터 제어 반복(**for**).  
  
 선택 및 반복 제어 구조를 중첩 및 누적하여 매우 복잡한 스크립트를 만들 수 있습니다.  
  
 구조적 프로그램 흐름의 세 번째 형식은 이 문서에서 다루지 않는 예외 처리를 통해 제공됩니다.  
  
## <a name="using-conditional-statements"></a>조건문 사용  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 **if** 및 [if...else](../javascript/reference/if-dot-dot-dot-else-statement-javascript.md) 조건문을 지원합니다. **if** 문에서는 조건이 테스트되고 조건이 테스트를 충족하면 관련 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드가 실행됩니다. `if...else` 문에서는 조건이 테스트에 실패할 경우 다른 코드가 실행됩니다. 가장 간단한 형식의 **if** 문은 한 줄로도 작성할 수 있지만 여러 줄로 된 **if** 문과 `if...else` 문이 훨씬 더 일반적입니다.  
  
 다음 예제에서는 **if** 문과 `if...else` 문에서 사용할 수 있는 구문을 보여 줍니다. 첫 번째 예제에서는 가장 간단한 부울 테스트를 보여 줍니다. 괄호 안의 항목이 **true**로 평가되거나 true로 강제 변환될 수 있는 경우에만 **if** 뒤의 문 또는 문 블록이 실행됩니다.  
  
```JavaScript  
function GetReaction(newShip, color, texture, dayOfWeek)  
{  
   // The test succeeds if the newShip Boolean value is true.  
   if (newShip)  
   {  
      return "Champagne Bottle";  
   }  
  
   // The test succeeds if both conditions are true.  
   if (color == "deep yellow" && texture == "large and small wrinkles")  
   {  
      return "Is it a crenshaw melon?";  
   }  
  
   // The test succeeds if either condition is true.  
   if ((dayOfWeek == "Saturday") || (dayOfWeek == "Sunday"))  
   {  
      return "I'm off to the beach!";  
   }  
   else  
   {  
      return "I'm going to work.";  
   }  
}  
  
var reaction = GetReaction(false, "deep yellow", "smooth", "Sunday");  
document.write(reaction);  
  
// Output: I'm off to the beach!  
```  
  
## <a name="conditional-operator"></a>조건 연산자  
 또한 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 암시적 조건 형태를 지원합니다. 이 스크립트에서는 조건 앞에 **if** 단어를 사용하는 대신 테스트할 조건 다음에 물음표를 사용합니다. 또한 조건이 충족되는 경우와 충족되지 않는 경우에 사용할 두 가지 대안을 지정합니다. 이러한 대안은 콜론을 사용하여 구분해야 합니다.  
  
```JavaScript  
var AMorPM = (theHour >= 12) ? "PM" : "AM";  
```  
  
 여러 조건을 함께 테스트해야 하는 경우 어느 한 조건이 다른 조건들보다 실패하거나 성공할 확률이 크다면 '단락(short circuit) 계산'이라는 기능을 사용하여 스크립트 실행 속도를 빠르게 할 수 있습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 논리 식을 평가할 때 결과를 산출하는 데 필요한 만큼의 하위 식만 평가합니다.  
  
 예를 들어, ((x == 123) && (y == 6))과 같은 AND 식에서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 먼저 x가 123인지 확인합니다. 그렇지 않으면 y가 6이어도 전체 식이 true가 될 수 없습니다. 이 경우 y에 대한 테스트는 수행되지 않고 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]가 **false** 값을 반환합니다.  
  
 마찬가지로 여러 조건 중 하나가 **true**여야 하는 경우(|| 연산자 사용) 하나의 조건이 테스트에 통과하는 즉시 테스트가 중지됩니다. 이러한 방식은 테스트할 조건에 함수 호출 또는 기타 복잡한 식의 실행이 포함된 경우에 유용합니다. 이 점을 염두에 두고 Or 식을 작성할 때는 **true**일 가능성이 가장 큰 조건을 먼저 배치합니다. And 식을 작성할 때는 **false**일 가능성이 가장 큰 조건을 먼저 배치하십시오.  
  
 이런 식으로 스크립트를 만들면 다음 예제와 같이 **runfirst()**가 0을 반환할 경우 **runsecond()**가 실행되지 않는다는 이점이 있습니다.  
  
```JavaScript  
if ((runfirst() == 0) || (runsecond() == 0)) {  
    // some code  
}  
```  
  
## <a name="using-loops"></a>루프 사용  
 문 또는 문 블록을 반복적으로 실행할 수 있는 방법에는 여러 가지가 있습니다. 일반적으로 반복적인 실행을 *루핑* 또는 *반복*이라고 합니다. 반복은 하나의 루프가 한 번 실행되는 것을 의미합니다. 반복은 일반적으로 한 변수를 테스트하여 제어되는데 여기서 변수의 값은 루프가 실행될 때마다 변경됩니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 [for](../javascript/reference/for-statement-javascript.md) 루프, [for...in](../javascript/reference/for-dot-dot-dot-in-statement-javascript.md) 루프, [while](../javascript/reference/while-statement-javascript.md) 루프, [do...while](../javascript/reference/do-dot-dot-dot-while-statement-javascript.md)의 네 가지 형식의 루프를 지원합니다.  
  
## <a name="using-for-loops"></a>루프 사용  
 **for** 문에서는 카운터 변수, 테스트 조건 및 카운터를 업데이트하는 동작을 지정합니다. 매번 루프가 반복되기 전에 조건이 테스트됩니다. 테스트가 성공적일 경우 루프 내부의 코드가 실행됩니다. 테스트가 실패할 경우 루프 내부의 코드가 실행되지 않으며 루프 바로 다음 코드 줄부터 프로그램을 계속 실행합니다. 루프가 실행된 후 카운터 변수는 다음 반복이 시작되기 전에 업데이트됩니다.  
  
 루핑 조건이 한 번도 만족되지 않으면 루프는 실행되지 않으며 테스트 조건이 항상 만족되면 무한 루프가 발생합니다. 루프가 전혀 실행되지 않는 경우는 필요할 때도 있지만 무한 루프가 발생하는 경우는 바람직하지 않으므로 루프 조건을 만들 때 주의하십시오.  
  
```JavaScript  
// The update expression ("icount++" in the following examples)  
// is executed at the end of the loop, after the block of  
// statements that forms the body of the loop is executed, and  
// before the condition is tested.  
  
// Set a limit of 10 on the loop.  
var howFar = 10;  
  
// Create an array called sum with 10 members, 0 through 9.  
var sum = new Array(howFar);  
sum[0] = 0;  
  
// Iterate from 0 through 9.  
var theSum = 0;  
for(var icount = 0; icount < howFar; icount++)  
{  
   theSum += icount;  
   sum[icount] = theSum;  
}  
  
// This code is not executed at all, because icount is not greater than howFar.  
var newSum = 0;  
for(var icount = 0; icount > howFar; icount++)  
{  
   newSum += icount;  
}  
  
// This is an infinite loop.  
var sum = 0;  
for(var icount = 0; icount >= 0; icount++)  
{  
   sum += icount;  
}  
```  
  
## <a name="using-forin-loops"></a>for...in 루프 사용  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 [개체](../javascript/objects-and-arrays-javascript.md)의 모든 사용자 정의 속성 또는 배열의 모든 요소를 통하여 단계별로 실행할 수 있는 특별한 종류의 루프를 제공합니다. `for...in` 루프의 루프 카운터는 숫자가 아니라 문자열입니다. 여기에는 현재 속성의 이름 또는 현재 배열 요소의 인덱스가 포함됩니다.  
  
```JavaScript  
// Create an object with some properties  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 1234";  
  
// Enumerate (loop through)_all the properties in the object  
for (var prop in myObject)  
{  
    // This displays "The property 'name' is James", etc.  
    document.write("The property '" + prop + "' is " + myObject[prop]);  
    // New line.  
    document.write("<br />");    
}  
```  
  
 `for...in` 루프는 VBScript의 `For Each...Next` 루프와 비슷하게 보이지만 작동 방식이 동일하지는 않습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]**for...in 루프**는 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 개체의 속성에 대해 반복해서 수행됩니다. VBScript **For Each...Next** 루프는 컬렉션의 항목에 대해 반복해서 수행됩니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 컬렉션에 대해 루프를 반복하려면 [Enumerator 개체](../javascript/reference/enumerator-object-javascript.md)를 사용하거나, 있을 경우 컬렉션 개체의 `forEach` 메서드를 사용해야 합니다. Internet Explorer의 개체와 같은 일부 개체의 경우 VBScript **For Each...Next** 루프 및 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]**for...in** 루프가 모두 지원되지만 대부분의 개체에서는 이 두 가지가 모두 지원되지 않습니다.  
  
## <a name="using-while-loops"></a>while 루프 사용  
 `while` 루프는 **for** 루프와 비슷합니다. 두 루프의 차이점은 `while` 루프에는 기본 제공 카운터 변수나 업데이트 식이 없다는 것입니다. 단순히 "이 코드를 n번 실행하는 것"보다 복잡한 규칙을 가지는 문이나 문 블록의 반복 실행을 제어하려면 `while` 루프를 사용합니다. 다음 예제에서는 Internet Explorer 개체 모델 및 `while` 루프를 사용하여 사용자에게 간단한 질문을 합니다.  
  
```JavaScript  
var x = 0;  
while ((x != 5) && (x != null))  
{  
    x = window.prompt("What is my favorite number?", x);  
}  
  
if (x == null)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```  
  
> [!NOTE]
>  `while` 루프에서는 명시적인 내장 카운터 변수를 사용하지 않으므로 다른 루프 형식보다 무한 루프에 빠지기 쉽습니다. 또한 루프 조건이 업데이트되는 시기와 위치를 알아내는 것이 어려운 경우도 있으므로 조건이 업데이트되지 않는 `while` 루프를 작성하는 것이 더 쉽습니다. 따라서 `while` 루프를 설계할 때에는 주의해야 합니다.  
  
 위에서 설명한 것처럼 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 while 루프와 비슷한 **do...while** 루프도 있습니다. do...while 루프는 루프의 시작이 아니라 끝에서 조건을 테스트하므로 항상 최소한 한 번은 실행됩니다. 예를 들어, 위의 루프는 다음과 같이 다시 작성할 수 있습니다.  
  
```JavaScript  
var x = 0;  
do  
{  
    x = window.prompt("What is my favorite number?", x);  
} while ((x != 5) && (x != null));  
  
if (x == null)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```  
  
## <a name="using-break-and-continue-statements"></a>break 문 및 continue 문 사용  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 [break](../javascript/reference/break-statement-javascript.md) 문은 일부 조건이 충족될 경우 루프의 실행을 중지하기 위해 사용됩니다. **break**는 `switch` 블록을 종결할 때에도 사용됩니다. [continue](../javascript/reference/continue-statement-javascript.md) 문을 사용하면 나머지 코드 블록을 생략하고 다음 반복으로 즉시 건너뛸 수 있습니다. 이와 동시에 루프가 **for** 또는 `for...in` 루프일 경우 카운터 변수를 업데이트합니다.  
  
 다음 예제에서는 이전 예제에 **break** 및 **continue** 문을 사용하여 루프를 제어하는 방법을 보여 줍니다.  
  
```JavaScript  
var x = 0;  
do  
{  
    x = window.prompt("What is my favorite number?", x);  
  
    // Did the user cancel? If so, break out of the loop  
    if (x == null)  
        break;  
  
    // Did they enter a number?  
    // If so, no need to ask them to enter a number.  
    if (Number(x) == x)  
        continue;  
  
    // Ask user to only enter in numbers  
    window.alert("Please only enter in numbers!");  
  
} while (x != 5)  
  
if (x != 5)  
    window.alert("You gave up!");  
else  
    window.alert("Correct answer!");  
```
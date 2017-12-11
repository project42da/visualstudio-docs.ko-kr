---
title: "함수(JavaScript) | Microsoft Docs"
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
helpviewer_keywords: intrinsic JavaScript functions
ms.assetid: e2a72b5a-3edd-43d8-95e8-91721b38c1c1
caps.latest.revision: "24"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fd5626af6417b5f0010545874bd15c86b30a303a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="functions-javascript"></a>함수(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 함수는 작업을 수행하고 값을 반환할 수도 있습니다. 경우에 따라 이들 값은 계산 또는 비교 결과입니다. 함수를 "전역 메서드"라고도 합니다.  
  
 함수는 여러 작업을 한 이름으로 결합합니다. 이를 통해 코드를 간소화할 수 있습니다. 문 집합을 작성하고 이름을 지정하고 나서 전체 집합을 호출하고 해당 집합에 필요한 정보를 전달하여 전체 집합을 실행할 수 있습니다.  
  
 함수 이름 뒤의 정보를 괄호로 묶는 방식으로 함수에 정보를 전달합니다. 함수에 전달되는 정보 조각을 인수 또는 매개 변수라고 합니다. 일부 함수는 인수를 전혀 사용하지 않지만 다른 함수는 인수를 하나 이상 사용합니다. 일부 함수에서 인수 수는 함수를 사용하는 방법에 따라 다릅니다.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 언어에 빌드되는 함수 및 사용자가 직접 만드는 함수의 두 가지 함수를 지원합니다.  
  
## <a name="built-in-functions"></a>기본 제공 함수  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 언어에는 여러 가지 기본 제공 함수가 포함됩니다. 일부 함수를 통해 식 및 특수 문자를 처리할 수 있지만 다른 함수는 문자열을 숫자 값으로 변환합니다.  
  
 기본 제공 함수에 대한 자세한 내용은 [JavaScript 메서드](../javascript/reference/javascript-methods.md)를 참조하세요.  
  
## <a name="creating-your-own-functions"></a>고유한 함수 만들기  
 고유한 함수를 만들고 필요할 때 사용할 수 있습니다. 함수 정의는 함수 문 및 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 문 블록으로 구성됩니다.  
  
 다음 예제의 **checkTriplet** 함수는 삼각형 변의 길이를 인수로 사용합니다. 인수를 기반으로 세 숫자가 피타고라스 수를 구성하는지 확인하여 이 삼각형이 정삼각형인지를 계산합니다. 정삼각형 빗변 길이의 제곱은 다른 두 변 길이의 제곱 합과 같습니다. checkTriplet 함수는 다른 두 함수의 하나를 호출하여 실제 테스트를 수행합니다.  
  
 테스트의 부동 소수점 버전에서는 매우 작은 수("엡실론")를 테스트 변수로 사용해야 합니다. 부동 소수점 계산의 불확실성 및 반올림 오차 때문에 해당하는 세 값이 정수로 확인되지 않는 한 세 숫자가 피타고라스 수를 구성하는지 직접 테스트하는 것은 좋지 않습니다. 직접 테스트가 더 정확하므로 이 예제의 코드에서는 테스트가 적절한지 확인하고 적절하면 해당 테스트를 사용합니다.  
  
```JavaScript  
var epsilon = 0.00000000001; // Some very small number to test against.  
  
// The test function for integers.  
function integerCheck(a, b, c)   
{  
   // The test itself.  
   if ( (a*a) == ((b*b) + (c*c)) )     
      return true;  
  
   return false;  
} // End of the integer checking function.  
  
// The test function for floating-point numbers.  
function floatCheck(a, b, c)     
{  
   // Make the test number.  
   var delta = ((a*a) - ((b*b) + (c*c)))  
  
   // The test requires the absolute value  
   delta = Math.abs(delta);  
  
   // If the difference is less than epsilon, then it's pretty close.  
   if (delta < epsilon)     
      return true;  
  
   return false;  
} // End of the floating-poing check function.  
  
// The triplet checker.   
function checkTriplet(a, b, c)  
{   
   // Create a temporary variable for swapping values  
   var d = 0;   
  
   // First, move the longest side to position "a".  
  
   // Swap a and b if necessary  
   if (b > a)  
   {  
      d = a;  
      a = b;  
      b = d;  
   }  
  
   // Swap a and c if necessary  
   if (c > a)  
   {  
      d = a;  
      a = c;  
      c = d;  
   }  
  
   // Test all 3 values. Are they integers?  
   if (((a % 1) == 0) && ((b % 1) == 0) && ((c % 1) == 0))  
   {   
      // If so, use the precise check.  
      return integerCheck(a, b, c);   
   }  
   else  
   {  
      // If not, get as close as is reasonably possible.  
      return floatCheck(a, b, c);   
   }  
} // End of the triplet check function.  
  
// The next three statements assign sample values for testing purposes.  
var sideA = 5;  
var sideB = 5;  
var sideC = Math.sqrt(50.001);  
  
// Call the function. After the call, 'result' contains the result.  
var result = checkTriplet(sideA, sideB, sideC);  
```  
  
<a name="Arrow"></a>   
## <a name="arrow-functions"></a>화살표 함수  
 화살표 함수 구문(`=>`)은 익명 함수를 지정하는 간단한 메서드를 제공합니다. 다음은 화살표 함수 구문입니다.  
  
```JavaScript  
([arg] [, arg]) => {  
    statements  
}  
```  
  
 괄호로 묶을 수 있는 화살표 왼쪽의 값은 함수에 전달되는 인수를 지정합니다. 함수에 대한 인수가 하나만 있으면 괄호가 필요하지 않습니다. 전달되는 인수가 없으면 괄호가 필요합니다. 화살표 오른쪽의 함수 정의는 식(예: `v + 1`)이거나 중괄호({})로 묶은 문 블록일 수 있습니다.  
  
> [!IMPORTANT]
>  화살표 함수 구문은 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서만 지원됩니다.  
  
 `new` 연산자를 화살표 함수와 함께 사용할 수 없습니다.  
  
 다음 코드 예제에서는 식에서 화살표 함수를 함수 정의로 사용하는 방법을 보여 줍니다. 첫 번째 예제에서는 v가 식에 인수로 전달됩니다. 두 번째 예제에서는 v 및 i가 식에 인수로 전달됩니다.  
  
```  
var evens = [2, 4, 6, 8];  
  
// Using standard syntax.  
var odds = evens.map(function(v) { return v + 1; });  
  
// Using arrow function syntax.  
// Add one to each value to produce output.  
var odds = evens.map(v => v + 1);  
  
// The following line of code adds the index value to the passed  
// in value to produce output.  
// Note: the second argument to the callback function in the map   
// method is the index value (i).  
var nums = evens.map((v, i) => v + i);  
  
console.log(odds);  
console.log(nums);  
  
// Output:  
// [object Array] [3, 5, 7, 9]  
// [object Array] [2, 5, 8, 11]  
```  
  
 다음 코드 예제에서는 문 블록에서 화살표 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var fives = new Array();  
  
// Statement block, re-using nums array from previous example.  
// Note: The first argument to the callback function in forEach  
// is the value of the array element (v).  
nums.forEach(v => {  
  if (v % 5 === 0)  
    fives.push(v);  
});  
  
console.log(fives);  
  
// Output:  
// [object Array] [5]  
```  
  
 표준 함수와 달리 화살표 함수는 `var self = this;`와 같은 해결 방법의 필요성을 제거하는 데 사용될 수 있는 주변 코드와 같은 어휘 `this` 개체를 공유합니다.  
  
 다음 예제에서는 화살표 함수 내의 `this` 개체 값이 주변 코드에서와 같음을 보여 줍니다(`bob` 변수를 계속 참조함).  
  
```JavaScript  
var bob = {  
  _name: "Bob",  
  _friends: ["Pete", "Joe", "Larry"],  
  printFriends() {  
    this._friends.forEach(f =>  
      console.log(this._name + " knows " + f));  
  }  
}  
  
// Output:  
// Bob knows Pete  
// Bob knows Joe  
// Bob knows Larry  
```  
  
 화살표 함수는 `this` 개체처럼 주변 코드와 같은 어휘 `arguments` 개체도 공유합니다.  
  
<a name="Default"></a>   
## <a name="default-parameters"></a>기본 매개 변수  
 매개 변수에 초기 값을 할당하여 함수에서 매개 변수의 기본 값을 지정할 수 있습니다. 기본값은 상수 값 또는 식일 수 있습니다.  
  
> [!IMPORTANT]
>  기본 매개 변수는 [!INCLUDE[jsv12textExp](../javascript/includes/jsv12textexp-md.md)]에서만 지원됩니다.  
  
 다음 예제에서 y의 기본값은 10이고 z의 기본값은 20입니다. 호출자가 두 번째 인수로 고유 값 또는 undefined를 전달하지 않는 한 함수에서는 y 값으로 10을 사용합니다. 호출자가 세 번째 인수로 고유 값 또는 undefined를 전달하지 않는 한 함수에서는 z 값으로 20을 사용합니다.  
  
```JavaScript  
var val = 20;  
  
function f(x, y=10, z=val) {  
  return x + y + z;  
}  
  
console.log(f(3));  
console.log(f(3, 3));  
console.log(f(3, 3, 3));  
  
// Output:  
// 33  
// 26  
// 9  
```  
  
<a name="Rest"></a>   
## <a name="rest-parameters"></a>Rest 매개 변수  
 spread 연산자 ()로 지정되는 Rest 매개 변수를 사용하여 함수 호출의 연속된 인수를 배열로 전환할 수 있습니다.  
  
 Rest 매개 변수를 사용하면 `arguments` 개체를 사용할 필요가 없습니다. Rest 매개 변수는 다음과 같은 여러 측면에서 `arguments` 개체와 다릅니다.  
  
-   Rest 매개 변수는 실제 배열 인스턴스이므로 배열에서 수행할 수 있는 작업을 지원합니다.  
  
-   Rest 매개 변수에는 개별(명명된) 인수로 전달되지 않는 연속 인수만 포함됩니다(반대로 `arguments` 개체에는 함수에 전달되는 모든 인수가 포함됨).  
  
> [!IMPORTANT]
>  Rest 매개 변수 및 spread 연산자는 [!INCLUDE[jsv12text](../javascript/includes/jsv12text-md.md)]에서만 지원됩니다.  
  
 다음 코드 예제에서 "hello" 및 true는 배열 값으로 전달되고 y 매개 변수에 저장됩니다. Rest 매개 변수는 함수의 마지막 매개 변수여야 합니다.  
  
```JavaScript  
function f(x, ...y) {  
  // y is an array.  
  return x * y.length;  
}  
  
console.log(f(3, "hello", true));  
  
// Output:  
// 6  
  
```  
  
 Spread 연산자의 추가 사용 방법에 대해서는 [Spread 연산자](../javascript/reference/spread-operator-decrement-dot-dot-dot-javascript.md)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 언어 참조](../javascript/javascript-language-reference.md)
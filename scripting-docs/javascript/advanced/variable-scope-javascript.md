---
title: "변수 범위(JavaScript) | Microsoft Docs"
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
  - "범위, JavaScript"
  - "변수 범위[JavaScript]"
  - "변수, 범위[JavaScript]"
ms.assetid: a811a9a6-856f-46e9-8be3-f2d22a0c245f
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# 변수 범위(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에는 전역 및 지역의 두 가지 범위가 있습니다.  함수 정의의 외부에 선언된 변수는 전역 변수이며 프로그램 전체에서 이 값에 액세스하여 수정할 수 있습니다.  함수 정의의 내부에 선언된 변수는 지역 변수입니다.  이 변수는 함수가 실행될 때마다 만들어지고 소멸되므로 함수 외부의 코드에서 액세스할 수 없습니다.  블록 범위 변수의 특별한 경우를 제외하고는 JavaScript는 블록 범위를 지원하지 않습니다\(중괄호 집합 `{. . .}`에서 새 범위를 정의\).  
  
## JavaScript의 범위  
 지역 변수는 전역 변수와 동일한 이름을 가질 수 있지만 전역 변수와 완전히 별개의 것입니다. 따라서 한 변수의 값을 변경해도 동일한 이름의 다른 변수에 영향을 미치지 않으며  로컬 버전은 로컬 버전이 선언된 함수 내부에서만 의미가 있습니다.  
  
```javascript  
// Global definition of aCentaur.  
var aCentaur = "a horse with rider,";  
  
// A local aCentaur variable is declared in this function.  
function antiquities(){  
  
   var aCentaur = "A centaur is probably a mounted Scythian warrior";  
}  
  
antiquities();  
aCentaur += " as seen from a distance by a naive innocent.";  
  
document.write(aCentaur);  
  
// Output: "a horse with rider, as seen from a distance by a naive innocent."  
```  
  
 JavaScript에서 변수는 속해 있는 범위의 처음에 선언된 것처럼 계산됩니다.  이 때문에 다음과 같이 예상치 않은 동작이 나타날 수 있습니다.  
  
```javascript  
var aNumber = 100;  
tweak();  
  
function tweak(){  
  
    // This prints "undefined", because aNumber is also defined locally below.  
    document.write(aNumber);  
  
    if (false)  
    {  
        var aNumber = 123;    
    }  
}  
```  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 함수를 실행할 때 모든 변수 선언\(예: `var someVariable;`\)을 먼저 찾아보고  `undefined`의 초기 값으로 변수를 만듭니다.  변수가 값을 사용하여 선언되면\(예: `var someVariable = "something";`\) 처음에는 `undefined` 값을 갖고 있다가 선언을 포함하는 줄이 실행될 때만 선언된 값을 취합니다.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서는 코드를 실행하기 전에 조건부 블록 내에 있든 다른 구문 내에 있든 관계없이 모든 변수 선언을 처리합니다.  [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 모든 변수를 찾았으면 함수 내의 코드를 실행합니다.  변수가 함수 내에 암시적으로 선언된 경우, 즉 할당 식의 왼쪽에 표시되지만 `var`을 사용하여 선언되지 않은 경우 전역 변수로 만들어집니다.  
  
 JavaScript에서 내부\(중첩된\) 함수는 반환된 후에도 함수 자체와 같은 범위에 있는 지역 변수에 참조를 저장합니다.  이 참조 집합을 클로저라고 합니다.  외부 함수에 대한 입력 매개 변수\(`name`\)는 내부 함수에 대한 클로저에 저장되는 지역 변수이므로 다음 예제에서 내부 함수에 대한 두 번째 호출은 첫 번째 호출과 같은 메시지\("Hello Bill"\)를 출력합니다.  
  
```javascript  
function send(name) {  
    // Local variable 'name' is stored in the closure  
    // for the inner function.  
    return function () {  
        sendHi(name);  
    }  
}  
  
function sendHi(msg) {  
    console.log('Hello ' + msg);  
}  
  
var func = send('Bill');  
func();  
// Output:  
// Hello Bill  
sendHi('Pete');  
// Output:  
// Hello Pete  
func();  
// Output:  
// Hello Bill  
```  
  
## 블록 범위 변수  
 Internet Explorer 11은 블록 범위 변수인 [let](../../javascript/reference/let-statement-javascript.md) 및 [const](../../javascript/reference/const-statement-javascript.md)에 대한 지원을 제공합니다.  이러한 변수에 대해 중괄호 `{. . .}`로 새 범위를 정의합니다.  이러한 변수 중 하나를 특정 값으로 설정하면 해당 값은 설정된 범위에만 적용됩니다.  
  
 다음 예제에서는 `let` 및 블록 범위 지정을 사용하는 방법을 보여 줍니다.  
  
> [!NOTE]
>  다음 코드는 Internet Explorer 11 표준 모드 이상에서 지원됩니다.  
  
```javascript  
let x = 10;  
var y = 10;  
{  
    let x = 5;  
    var y = 5;  
    {  
        let x = 2;  
        var y = 2;  
        document.write("x: " + x + "<br/>");  
        document.write("y: " + y + "<br/>");  
        // Output:  
        // x: 2  
        // y: 2  
    }  
    document.write("x: " + x + "<br/>");  
    document.write("y: " + y + "<br/>");  
    // Output:  
    // x: 5  
    // y: 2  
}  
  
document.write("x: " + x + "<br/>");  
document.write("y: " + y + "<br/>");  
// Output:  
// x: 10  
// y: 2  
```
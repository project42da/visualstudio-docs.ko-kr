---
title: "Strict 모드(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- VS.WebClient.Help.SCRIPT1038
- VS.WebClient.Help.SCRIPT1050
- VS.WebClient.Help.SCRIPT1042
- VS.WebClient.Help.SCRIPT1041
- VS.WebClient.Help.SCRIPT1046
- VS.WebClient.Help.SCRIPT1045
- VS.WebClient.Help.SCRIPT1037
- VS.WebClient.Help.SCRIPT1039
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strict mode
- use strict
ms.assetid: 0f27022a-f41c-4504-965c-5a2701f342cd
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 77ee7d54dd265026b2bf4c9af52a71cccf9a7675
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="strict-mode-javascript"></a>Strict 모드(JavaScript)
strict 모드는 코드에 더 나은 오류 검사를 적용하는 방법입니다. strict 모드를 사용하면, 예를 들어 암시적으로 선언한 변수를 사용하거나 읽기 전용 속성에 값을 할당하거나 확장할 수 없는 개체에 속성을 추가할 수 없습니다. 제한사항은 이 항목 뒷부분의 코드에 적용되는 [Strict 모드의 코드 제한사항](../../javascript/advanced/strict-mode-javascript.md#rest) 섹션에 나와 있습니다. Strict 모드에 대한 추가 정보는 [ECMAScript 언어 사양(5번째 버전)](http://www.ecma-international.org/publications/standards/Ecma-262.htm)을 참조하세요.  
  
> [!WARNING]
>  strict 모드는 Internet Explorer 10 이전의 Internet Explorer 버전에서 지원되지 않습니다.  
  
## <a name="declaring-strict-mode"></a>strict 모드 선언  
 파일, 프로그램 또는 함수의 시작 부분에 `"use strict";`를 추가하여 strict 모드를 선언할 수 있습니다. 이 종류의 선언을 *지시문 프롤로그*라고 합니다. strict 모드 선언 범위는 컨텍스트에 따라 달라집니다. 전역 컨텍스트(함수 범위 밖)에서 선언되는 경우 프로그램의 모든 코드에 strict 모드가 적용됩니다. 함수 내에서 선언되는 경우 함수의 모든 코드에 strict 모드가 적용됩니다. 예를 들어 다음 예제에서는 모든 코드에 strict 모드가 적용되며 함수 밖의 변수 선언 시 "strict 모드에서 변수가 정의되지 않았습니다" 구문 오류가 발생합니다.  
  
```JavaScript  
"use strict";  
function testFunction(){  
    var testvar = 4;  
    return testvar;  
}  
  
// This causes a syntax error.  
testvar = 5;  
  
```  
  
 다음 예제에서는 `testFunction` 내 코드에만 strict 모드가 적용됩니다. 함수 밖 변수 선언의 경우 구문 오류가 발생하지 않지만 함수 내 선언의 경우 구문 오류가 발생합니다.  
  
```JavaScript  
function testFunction(){  
    "use strict";  
    // This causes a syntax error.  
    testvar = 4;  
    return testvar;  
}  
testvar = 5;  
  
```  
  
<a name="rest"></a>   
## <a name="restrictions-on-code-in-strict-mode"></a>코드에 적용되는 strict 모드의 제한  
 다음 표에서는 strict 모드에 적용되는 가장 중요한 제한을 보여 줍니다.  
  
|||||  
|-|-|-|-|  
|**언어 요소**|**제한 사항**|**오류**|**예제**|  
|변수|선언하지 않고 변수를 사용합니다.|SCRIPT5042: Strict 모드에서 변수가 정의되지 않았습니다.|`testvar = 4;`|  
|읽기 전용 속성|읽기 전용 속성에 씁니다.|SCRIPT5045: Strict 모드에서는 읽기 전용 속성에 할당할 수 없습니다.|`var testObj = Object.defineProperties({}, {     prop1: {         value: 10,         writable: false // by default     },     prop2: {         get: function () {         }     } }); testObj.prop1 = 20;  testObj.prop2 = 30;`|  
|확장할 수 없는 속성|`extensible` 특성이 `false`로 설정된 개체에 속성을 추가합니다.|SCRIPT5046: 확장할 수 없는 개체의 속성을 만들 수 없습니다.|`var testObj = new Object();  Object.preventExtensions(testObj);  testObj.name = "Bob";`|  
|`delete`|변수, 함수 또는 인수를 삭제합니다.<br /><br /> `configurable` 특성이 `false`로 설정된 속성을 삭제합니다.|SCRIPT1045: Strict 모드에서는 \<expression>에 대해 delete를 호출할 수 없습니다.|`var testvar = 15; function testFunc() {}; delete testvar; delete testFunc;  Object.defineProperty(testObj, "testvar", {     value: 10,     configurable: false     }); delete testObj.testvar;`|  
|속성 중복|개체 리터럴에서 속성을 두 번 이상 정의합니다.|SCRIPT1046: strict 모드에서는 한 속성을 여러 번 정의할 수 없습니다.|`var testObj = {     prop1: 10,     prop2: 15,     prop1: 20 };`|  
|매개 변수 이름 중복|함수에서 매개 변수 이름을 두 번 이상 사용합니다.|SCRIPT1038: strict 모드에서는 정식 매개 변수 이름이 중복될 수 없습니다.|`function testFunc(param1, param1) {     return 1; };`|  
|다음에 사용하기 위한 예약된 키워드|다음에 사용하기 위한 예약된 키워드를 변수 또는 함수 이름으로 사용합니다.|SCRIPT1050: 식별자에 대해 다음에 사용하기 위한 예약어를 잘못 사용했습니다. strict 모드에서는 식별자 이름이 예약됩니다.|-                      `implements`<br /><br /> -                      `interface`<br /><br /> -                      `package`<br /><br /> -                      `private`<br /><br /> -                      `protected`<br /><br /> -                      `public`<br /><br /> -                      `static`<br /><br /> -                      `yield`|  
|8진수|숫자 리터럴에 8진수 값을 할당하거나 8진수 값에 이스케이프를 사용하려고 합니다.|SCRIPT1039: strict 모드에서는 8진수 숫자 리터럴 및 이스케이프 문자를 사용할 수 없습니다.|`var testoctal = 010; var testescape = \010;`|  
|`this`|`this`의 값이 `null` 또는 `undefined`인 경우 전역 개체로 변환되지 않습니다.||`function testFunc() {     return this; } var testvar = testFunc();`<br /><br /> strict 모드가 아닌 경우 `testvar` 값은 전역 개체이지만 strict 모드에서 이 값은 `undefined`입니다.|  
|식별자인 `eval`|문자열 "eval"은 식별자(변수 또는 함수 이름, 매개 변수 이름 등)로 사용할 수 없습니다.||`var eval = 10;`|  
|문 또는 블록 내에서 선언된 함수|문 또는 블록 내에서 함수를 선언할 수 없습니다.|SCRIPT1047: strict 모드에서는 함수 선언을 문이나 블록 내에 중첩할 수 없습니다. 함수 선언은 함수 본문 내에 직접 나오거나 최상위 수준에만 나와야 합니다.|`var arr = [1, 2, 3, 4, 5]; var index = null; for (index in arr) {     function myFunc() {}; }`|  
|`eval` 함수 내에서 선언된 변수|변수가 `eval` 함수 내에서 선언되는 경우 해당 함수 밖에서 사용할 수 없습니다.|SCRIPT1041: strict 모드에서 'eval'을 잘못 사용했습니다.|`eval("var testvar = 10"); testvar = 15;`<br /><br /> 간접 계산이 가능하지만 `eval` 함수 외부에 선언된 변수는 여전히 사용할 수 없습니다.<br /><br /> `var indirectEval = eval; indirectEval("var testvar = 10;"); document.write(testVar);`<br /><br /> 이 코드는 "SCRIPT5009: 'testVar'이 정의되지 않았습니다" 오류를 발생시킵니다.|  
|식별자인 `Arguments`|문자열 "arguments"는 식별자(변수 또는 함수 이름, 매개 변수 이름 등)로 사용할 수 없습니다.|SCRIPT1042: strict 모드에서 'arguments'를 잘못 사용했습니다.|`var arguments = 10;`|  
|함수 내 `arguments`|로컬 `arguments` 개체의 멤버 값을 변경할 수 없습니다.||`function testArgs(oneArg) {     arguments[0] = 20; }`<br /><br /> strict 모드가 아닌 경우 `oneArg` 값을 변경하여 `arguments[0]` 매개 변수의 값을 변경할 수 있습니다. 그러면 `oneArg` 및 `arguments[0]`의 값이 모두 20이 됩니다. strict 모드에서 `arguments[0]` 값을 변경해도 `oneArg` 값에 영향을 주지 않습니다. `arguments` 개체가 로컬 복사본이기 때문입니다.|  
|`arguments.callee`|허용되지 않습니다.||`function (testInt) {     if (testInt-- == 0)         return;     arguments.callee(testInt--); }`|  
|`with`|허용되지 않습니다.|SCRIPT1037: strict 모드에서는 'with' 문을 사용할 수 없습니다.|`with (Math){     x = cos(3);     y = tan(7); }`|
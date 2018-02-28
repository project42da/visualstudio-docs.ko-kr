---
title: "데이터 형식(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Boolean data type, supported data types
ms.assetid: c7a6bd3a-4b1c-4dbe-8505-106dbf483b41
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aa3a0e4cdbb25019758f89958afdf06c11f01a34
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="data-types-javascript"></a>데이터 형식(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 세 개의 기본 데이터 형식, 두 개의 복합 데이터 형식 및 두 개의 특수 데이터 형식이 있습니다.  
  
## <a name="primary-data-types"></a>기본 데이터 형식  
 기본(원시) 데이터 형식은 다음과 같습니다.  
  
-   문자열  
  
-   수  
  
-   부울  
  
## <a name="composite-data-types"></a>복합 데이터 형식  
 복합(참조) 데이터 형식은 다음과 같습니다.  
  
-   개체  
  
-   배열  
  
## <a name="special-data-types"></a>특수 데이터 형식  
 특수 데이터 형식은 다음과 같습니다.  
  
-   Null  
  
-   Undefined  
  
## <a name="string-data-type"></a>String 데이터 형식  
 문자열 값은 일련의 유니코드 문자(0개 이상의 문자, 숫자 및 문장 부호)입니다. 문자열 데이터 형식을 사용하여 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 텍스트를 나타냅니다. 스크립트에 문자열 리터럴을 포함시키려면 작은따옴표 또는 큰따옴표로 묶습니다. 큰따옴표는 작은따옴표로 묶은 문자열에 포함될 수 있고, 작은따옴표는 큰따옴표로 묶은 문자열에 포함될 수 있습니다. 다음은 문자열의 예제입니다.  
  
```JavaScript  
"Happy am I; from care I'm free!"  
'"Avast, ye lubbers!" roared the technician.'   
"45"  
'c'  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 단일 문자를 나타내는 형식이 없습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 단일 문자를 나타내려면 한 문자만으로 구성된 문자열을 만듭니다. 0개 문자("")가 포함된 문자열은 빈 문자열(길이가 0)입니다.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 직접 입력할 수 없는 문자를 만들기 위해 문자열에 포함시킬 수 있는 이스케이프 시퀀스를 제공합니다. 예를 들어 `\t`는 탭 문자를 지정합니다. 자세한 내용은 [특수 문자](../javascript/advanced/special-characters-javascript.md)를 참조하세요.  
  
## <a name="number-data-type"></a>숫자 데이터 형식  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 정수와 부동 소수점 값 사이에는 차이가 없습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 숫자는 둘 중 하나일 수 있습니다([!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 내부적으로 모든 숫자를 부동 소수점 값으로 나타냄).  
  
### <a name="integer-values"></a>정수 값  
 정수 값은 양의 정수, 음의 정수 및 0일 수 있습니다. base 10(10진수), base 16(16진수) 및 base 8(8진수)로 나타낼 수 있습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 대부분의 숫자는 10진수로 작성됩니다.  
  
 16진수("hex") 정수는 선행 "0x"(0 및 x&#124;X)를 접두사로 붙여 표시합니다. 0-9 숫자 및 A-F 문자(대문자 또는 소문자)만 포함할 수 있습니다. A-F 문자는 base 10의 10-15를 한 자리 숫자로 나타내는 데 사용됩니다. 즉 0xF는 15와 같고 0x10은 16과 같습니다.  
  
 8진수는 선행 "0"(영)을 접두사로 붙여 표시합니다. 0-7 숫자만 포함할 수 있습니다. 선행 "0"이 있고 숫자 "8" 및/또는 "9"를 포함한 숫자는 10진수로 해석됩니다.  
  
 16진수와 8진수는 모두 음수일 수 있지만 소수 부분이 없으며, 과학적(지수) 표기법으로 작성할 수 없습니다.  
  
> [!NOTE]
>  [!INCLUDE[jsv9text](../javascript/includes/jsv9text-md.md)]에서 시작하는 [parseInt 함수](../javascript/reference/parseint-function-javascript.md)는 접두사가 "0"인 문자열을 8진수로 처리하지 않습니다. 그러나 `parseInt` 함수를 사용하지 않는 경우에는 접두사가 "0"인 문자열을 여전히 8진수로 해석할 수 있습니다.  
  
### <a name="floating-point-values"></a>부동 소수점 값  
 부동 소수점 값은 소수 부분이 있는 정수가 될 수 있습니다. 또한 과학적 표기법으로 나타낼 수 있습니다. 즉 "e"(대문자 또는 소문자)는 "10의 거듭제곱"을 나타내는 데 사용됩니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 숫자 표현에 대한 8바이트 IEEE 754 부동 소수점 표준을 사용하여 숫자를 나타냅니다. 즉 1.79769x10<sup>308</sup>만큼 큰 숫자 및 5x10<sup>-324</sup>만큼 작은 숫자를 작성할 수 있습니다. 소수점을 포함하고 소수점 앞에 하나의 "0"이 있는 숫자는 10진수 부동 소수점 숫자로 해석됩니다.  
  
 "0x" 또는 "00"으로 시작하고 소수점을 포함한 숫자는 오류를 생성합니다. 다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 숫자의 몇 가지 예입니다.  
  
|수|설명|해당 10진수|  
|------------|-----------------|------------------------|  
|.0001, 0.0001, 1e-4, 1.0e-4|동등한 4개의 부동 소수점 숫자|0.0001|  
|3.45e2|부동 소수점 숫자입니다.|345|  
|45|정수입니다.|45|  
|0378|정수입니다. 8진수(0으로 시작)처럼 보이지만 8이 유효한 8진수가 아니므로 이 숫자는 10진수로 처리됩니다.|378|  
|0377|8진수 정수입니다. 위의 숫자보다 하나가 작은 것으로 보이지만 실제 값은 매우 다릅니다.|255|  
|0.0001|부동 소수점 숫자. 0으로 시작하지만 소수점이 있으므로 8진수가 아닙니다.|0.0001|  
|00.0001|오류입니다. 두 개의 선행 0은 숫자를 8진수로 표시하지만 8진수는 10진수 구성 요소를 사용할 수 없습니다.|해당 없음(컴파일러 오류)|  
|0Xff|16진수 정수|255|  
|0x37CF|16진수 정수|14287|  
|0x3e7|16진수 정수 'e'는 지수로 처리되지 않습니다.|999|  
|0x3.45e2|오류입니다. 16진수 숫자에는 소수 부분이 없습니다.|해당 없음(컴파일러 오류)|  
  
 또한 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 특수 값이 있는 숫자가 포함됩니다. 이러한 항목은 다음과 같습니다.  
  
-   NaN(숫자가 아님) - 문자열 또는 정의되지 않은 값과 같이 잘못된 데이터에 대해 수학 연산을 수행할 때 사용됩니다.  
  
-   양의 무한대 - 양수가 너무 커서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에 나타낼 수 없을 때 사용됩니다.  
  
-   음의 무한대 - 음수가 너무 커서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에 나타낼 수 없을 때 사용됩니다.  
  
-   양의 0 및 음의 0 - [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 양의 0과 음의 0을 구별합니다.  
  
## <a name="boolean-data-type"></a>Boolean 데이터 형식  
 문자열 및 숫자 데이터 형식은 거의 무제한의 다른 값을 가질 수 있지만, 부울 데이터 형식은 두 개만 가질 수 있습니다. 즉 리터럴 `true` 및 `false`입니다. 부울 값은 진리 값입니다. 조건이 참인지 여부를 지정합니다.  
  
 스크립트에서 비교하면 항상 부울 결과가 있습니다. 다음 줄의 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드를 살펴보겠습니다.  
  
```JavaScript  
y = (x == 2000);  
```  
  
 여기서 `x` 변수의 값은 숫자(2000)와 비교됩니다. 일치하는 경우 비교 결과는 **true** 부울 값이며 `y` 변수에 할당됩니다. `x`가 2000과 같지 않으면 비교 결과는 `false` 부울 값입니다.  
  
 부울 값은 제어 구조에서 특히 유용합니다. 다음 코드는 부울 값을 사용하는 명령문과 해당 부울 값을 직접 만드는 비교를 결합합니다. 다음 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드 샘플을 살펴보겠습니다.  
  
```JavaScript  
if (x == 2000) {  
    z = z + 1;  
}  
else {  
    x = x + 1;  
}  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 `if/else` 문은 부울 값이 `true`(`z = z + 1`)이면 하나의 작업을 수행하고, `false`(`x = x + 1`)이면 대체 작업을 수행합니다.  
  
 모든 식을 비교 식으로 사용할 수 있습니다. 0, null, undefined 또는 빈 문자열로 평가되는 식은 `false`로 해석됩니다. 다른 값으로 평가 되는 식은 `true`로 해석됩니다. 예를 들어 다음과 같은 식을 사용할 수 있습니다.  
  
```JavaScript  
// This may not do what you expect. See below!  
if (x = y + z)   
```  
  
 위의 줄은 하나의 등호(할당 연산자)만 사용하므로 `x`가 `y + z`와 같은지 여부를 확인하지 않습니다. 대신, 위 코드는 `x` 변수에 `y + z`의 값을 할당한 다음 전체 식의 결과(`x`의 값)가 0인지 확인합니다. `x`가 `y + z`와 같은지 확인하려면 다음 코드를 사용해야 합니다.  
  
```JavaScript  
// This is different from the code above!  
if (x == y + z)   
```  
  
 비교에 대한 자세한 내용은 [프로그램 흐름 제어](../javascript/controlling-program-flow-javascript.md)를 참조하세요.  
  
## <a name="the-null-data-type"></a>null 데이터 형식  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 `null` 데이터 형식에는 하나의 값(null)만 있습니다. `null` 키워드는 함수 또는 변수의 이름으로 사용할 수 없습니다.  
  
 `null`을 포함하는 변수에는 유효한 숫자, 문자열, 부울, 배열 또는 개체가 없습니다. `null` 값을 변수에 할당하여 해당 변수의 내용을 지울 수 있습니다(변수는 삭제하지 않음).  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 `null`은 C 및 C++와는 달리 0과 같지 않습니다. 또한 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 `typeof` 연산자는 `null` 값을 `null` 형식이 아니라 `Object` 형식으로 보고합니다. 잠재적으로 혼란스러운 이 동작은 이전 버전과의 호환성을 위한 것입니다.  
  
## <a name="the-undefined-data-type"></a>정의되지 않은 데이터 형식  
 존재하지 않는 개체 속성 또는 선언되었지만 할당된 값이 전혀 없는 변수를 사용하면 `undefined` 값이 반환됩니다.  
  
 변수 형식을 "undefined" 문자열과 비교하여 변수 형식이 `undefined`인지 확인할 수 있지만, 변수를 `undefined`와 비교하여 해당 변수가 있는지 확인할 수 있습니다. 다음 예제에서는 `x` 변수가 선언되었는지 확인하는 방법을 보여 줍니다.  
  
```JavaScript  
  
var x;  
  
// This method works.  
if (x == undefined) {  
    document.write("comparing x to undefined <br/>");  
}  
.  
// This method doesn't work - you must check for the string "undefined".  
if (typeof(x) == undefined) {  
    document.write("comparing the type of x to undefined <br/>");  
}  
// This method does work.   
if (typeof(x) == "undefined") {  
    document.write("comparing the type of x to the string 'undefined'");  
}  
  
// Output:   
// comparing x to undefined   
// comparing the type of x to the string 'undefined'  
  
```  
  
 정의되지 않은 값을 `null`과 비교할 수도 있습니다. `someObject.prop` 속성이 `null`이거나 `someObject.prop` 속성이 없는 경우 이 비교는 `true`입니다.  
  
```JavaScript  
someObject.prop == null;  
```  
  
 개체 속성이 있는지 확인하려면 다음과 같이 **in** 연산자를 사용할 수 있습니다.  
  
```JavaScript  
if ("prop" in someObject)  
    // someObject has the property 'prop'  
```  
  
## <a name="see-also"></a>참고 항목  
 [개체 및 배열](../javascript/objects-and-arrays-javascript.md)   
 [typeof 연산자](../javascript/reference/typeof-operator-decrementjavascript.md)
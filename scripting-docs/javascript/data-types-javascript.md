---
title: "데이터 형식(JavaScript) | Microsoft Docs"
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
  - "Boolean 데이터 형식, 지원되는 데이터 형식"
ms.assetid: c7a6bd3a-4b1c-4dbe-8505-106dbf483b41
caps.latest.revision: 35
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 35
---
# 데이터 형식(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 기본 데이터 형식 3개, 복합 데이터 형식 2개 및 특수 데이터 형식 2개가 있습니다.  
  
## 기본 데이터 형식  
 기본 데이터 형식은 다음과 같습니다.  
  
-   문자열  
  
-   숫자  
  
-   Boolean  
  
## 복합 데이터 형식  
 복합\(참조\) 데이터 형식은 다음과 같습니다.  
  
-   개체  
  
-   배열  
  
## 특수 데이터 형식  
 특수 데이터 형식은 다음과 같습니다.  
  
-   Null  
  
-   정의되어 있지 않습니다.  
  
## String 데이터 형식  
 문자열 값은 0개 이상의 유니코드 문자\(글자, 숫자 및 문장 부호\)가 연결되어 있습니다.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 문자열 데이터 형식을 사용하여 텍스트를 나타냅니다.  작은따옴표 또는 큰따옴표 쌍으로 문자열 리터럴을 묶어 스크립트에 포함시킬 수 있습니다.  큰따옴표는 작은따옴표로 묶인 문자열 안에 포함될 수 있으며 작은따옴표는 큰따옴표로 묶인 문자열 안에 포함될 수 있습니다.  다음은 이러한 문자열의 예제입니다.  
  
```javascript  
"Happy am I; from care I'm free!"  
'"Avast, ye lubbers!" roared the technician.'   
"45"  
'c'  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 단일 문자를 나타내는 형식이 없습니다.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 단일 문자를 나타내려면 한 문자로만 구성된 문자열을 만듭니다.  문자가 포함되지 않은 문자열\(""\)은 길이가 0인 빈 문자열입니다.  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 직접 입력할 수 없는 문자를 만들기 위해 문자열에 포함시킬 수 있는 이스케이프 시퀀스를 제공합니다.  예를 들어 `\t`는 탭 문자를 지정합니다.  자세한 내용은 [특수 문자](../javascript/advanced/special-characters-javascript.md)을\(를\) 참조하십시오.  
  
## Number 데이터 형식  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 정수 및 부동 소수점 값이 구분되지 않습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 숫자는 둘 중 하나일 수 있습니다. 내부적으로 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 모든 숫자를 부동 소수점 값으로 나타냅니다.  
  
### 정수 값  
 정수 값은 양의 정수, 음의 정수 및 0일 수 있습니다.  정수는 10진수, 16진수 및 8진수로 표시할 수 있습니다.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 대부분의 숫자는 10진수로 작성됩니다.  
  
 16진수\("hex"\) 정수를 표시할 때는 앞에 "0x"\(숫자 0과 영문자 x&#124;X\)를 추가합니다.  16진수는 0부터 9까지의 숫자와 A부터 F까지의 영문자\(대문자 또는 소문자\)만 포함할 수 있습니다.  A부터 F까지 영문자는 단일 숫자로 10진수 10부터 15까지를 나타내는 데 사용됩니다.  즉, 0xF는 15이고 0x10은 16입니다.  
  
 8진수 정수를 표시할 때는 앞에 숫자 "0"을 추가합니다.  8진수는 0부터 7까지의 숫자만 포함합니다.  "0"으로 시작하고 "8" 및\/또는 "9"를 포함하는 숫자는 10진수로 해석됩니다.  
  
 16진수와 8진수는 모두 음수일 수 있지만 소수점 이하 자리를 가질 수 없으며 과학적\(지수\) 표기법으로 작성할 수 없습니다.  
  
> [!NOTE]
>  [!INCLUDE[jsv9text](../javascript/includes/jsv9text-md.md)]부터 [parseInt 함수](../javascript/reference/parseint-function-javascript.md)는 앞에 숫자 "0"이 추가된 문자열을 8진수로 처리하지 않습니다.  그러나 `parseInt` 함수를 사용하지 않는 경우에는 앞에 숫자 "0"이 추가된 문자열이 8진수로 해석될 수 있습니다.  
  
### 부동 소수점 값  
 부동 소수점 값은 소수점 이하 자리가 있는 정수일 수 있습니다.  과학적 표기법으로 나타낼 수도 있습니다.  즉, 대문자 또는 소문자 "e"는 "10의 거듭제곱"을 나타내는 데 사용됩니다.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 8바이트 IEEE 754 부동 소수점 표준을 숫자 표현에 사용하여 숫자를 나타냅니다.  즉, 1.79769x10<sup>308</sup>만큼 큰 숫자와 5x10<sup>-324</sup>만큼 작은 숫자를 작성할 수 있습니다.  소수점이 있고 소수점 앞에 하나의 "0"이 포함된 숫자는 10진수 부동 소수점 수로 해석됩니다.  
  
 "0x" 또는 "00"으로 시작하고 소수점이 있는 숫자를 사용하면 오류가 발생합니다.  다음은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 숫자에 대한 예제입니다.  
  
|숫자|설명|해당 10진수 값|  
|--------|--------|---------------|  
|.0001, 0.0001, 1e\-4, 1.0e\-4|모두 같은 값을 갖는 부동 소수점 수입니다.|0.0001|  
|3.45e2|부동 소수점 수.|345|  
|45|정수입니다.|45|  
|0378|정수입니다.  0으로 시작하여 8진수 같아 보이지만 8은 8진법에 적합한 숫자가 아니므로 10진수로 간주됩니다.|378|  
|0377|8진 정수.  위에 있는 숫자보다 하나 작은 수로 보이지만 실제 값은 완전히 다릅니다.|255|  
|0.0001|부동 소수점 수.  0으로 시작하지만 소수점이 있으므로 8진수가 아닙니다.|0.0001|  
|00.0001|오류가 발생합니다.  앞에 두 개의 0이 있으므로 숫자가 8진수로 표시되지만 10진수는 소수 구성 요소가 허용되지 않습니다.|N\/A\(컴파일러 오류\)|  
|0Xff|16진 정수.|255|  
|0x37CF|16진 정수.|14287|  
|0x3e7|16진 정수.  문자 'e'는 지수 연산자\(^\)로 처리되지 않습니다.|999|  
|0x3.45e2|오류가 발생합니다.  16진수는 소수점 이하 자리를 가질 수 없습니다.|N\/A\(컴파일러 오류\)|  
  
 또한 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에는 특수 값을 가진 숫자가 포함됩니다.  나타낼 수 있습니다.  
  
-   NaN\(숫자가 아님\).  문자열이나 정의되지 않은 값 등 부적절한 데이터에 대해 수학 연산이 수행될 때 사용됩니다.  
  
-   양수 Infinity.  양수가 너무 커서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 표시할 수 없을 때 사용됩니다.  
  
-   음수 Infinity.  음수가 너무 커서 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 표시할 수 없을 때 사용됩니다.  
  
-   양수 0 및 음수 0.  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 양수 0과 음수 0이 구분됩니다.  
  
## Boolean 데이터 형식  
 문자열 데이터 형식과 숫자 데이터 형식은 실제로 다른 값을 무제한으로 가질 수 있지만 부울 데이터 형식은 두 개만 가질 수 있습니다.  이는 리터럴 `true` 및 `false`입니다.  부울 값은 참 값이며 조건이 참인지 여부를 지정합니다.  
  
 스크립트에서 비교 결과는 항상 부울입니다.  다음 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드 줄을 살펴봅니다.  
  
```javascript  
y = (x == 2000);  
```  
  
 여기서 변수 `x`의 값이 숫자 2000과 비교됩니다.  같은 경우 비교 결과는 부울 값 **true**이며 이 값은 변수 `y`에 할당됩니다.  `x`가 2000과 같지 않으면 비교 결과는 부울 값 `false`입니다.  
  
 부울 값은 제어 구조에서 특히 유용합니다.  다음 코드는 부울 값을 만드는 비교와 이 값을 사용하는 문을 직접 결합합니다.  다음과 같은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 코드 샘플을 살펴봅니다.  
  
```javascript  
if (x == 2000) {  
    z = z + 1;  
}  
else {  
    x = x + 1;  
}  
```  
  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 `if/else` 문은 부울 값이 `true` \(`z = z + 1`\)인 경우 한 동작을 수행하고 부울 값이 `false` \(`x = x + 1`\)인 경우 대체 동작을 수행합니다.  
  
 아무 식이나 비교 식으로 사용할 수 있습니다.  0, null, 정의되지 않음 또는 빈 문자열로 평가되는 모든 식은 `false`로 해석됩니다.  다른 값으로 평가되는 식은 `true`로 해석됩니다.  예를 들어, 다음과 같이 식을 사용할 수 있습니다.  
  
```javascript  
// This may not do what you expect. See below!  
if (x = y + z)   
```  
  
 위의 줄에서는 하나의 등호\(할당 연산자\)만 사용하므로 `x`가 `y + z`와 같은지 확인하지 않습니다.  대신 위의 코드는 `y + z`의 값을 변수 `x`에 할당한 다음 전체 식의 결과\(`x` 값\)가 0인지 검사합니다.  `x`가 `y + z`와 같은지 검사하려면 다음 코드를 사용해야 합니다.  
  
```javascript  
// This is different from the code above!  
if (x == y + z)   
```  
  
 비교에 대한 자세한 내용은 [프로그램 흐름 비교](../javascript/controlling-program-flow-javascript.md)를 참조하세요.  
  
## null 데이터 형식  
 `null` 데이터 형식은 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 하나의 값인 null만 갖습니다.  `null` 키워드는 함수 또는 변수의 이름으로 사용할 수 없습니다.  
  
 `null`을 포함하는 변수에 유효하지 않은 숫자, 문자열, 부울, 배열 또는 개체가 포함되어 있습니다.  변수에 `null` 값을 할당하면 변수를 삭제하지 않고 변수의 내용을 지울 수 있습니다.  
  
 C 및 C\+\+에서와 마찬가지로 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 `null`은 0과 같지 않습니다.  또한 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 `typeof` 연산자는 `null` 값을 `null` 형식이 아닌 `Object` 형식으로 보고합니다.  다소 혼동의 여지가 있지만 이전 버전과의 호환성을 위해 이러한 기능이 제공됩니다.  
  
## 정의되지 않은 데이터 형식  
 `undefined` 값은 존재하지 않는 개체 속성을 사용하거나 선언되었지만 값이 할당되지 않은 변수를 사용할 때 반환됩니다.  
  
 변수의 형식을 문자열 "undefined"와 비교하여 형식이 `undefined`인지 확인할 수 있지만 `undefined`와 비교하여 변수가 존재하는지 확인할 수 있습니다.  다음 예제에서는 변수 `x`가 선언되었는지 확인하는 방법을 보여줍니다.  
  
```javascript  
  
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
  
 또한 정의되지 않은 값을 `null`과 비교할 수도 있습니다.  이 비교는 속성 `someObject.prop`이 `null`이거나 속성 `someObject.prop`이 존재하지 않는 경우 `true`입니다.  
  
```javascript  
someObject.prop == null;  
```  
  
 개체 속성이 있는지 검사하려면 **in** 연산자를 사용할 수 있습니다.  
  
```javascript  
if ("prop" in someObject)  
    // someObject has the property 'prop'  
```  
  
## 참고 항목  
 [Object 및 Array](../javascript/objects-and-arrays-javascript.md)   
 [typeof 연산자](../javascript/reference/typeof-operator-decrementjavascript.md)
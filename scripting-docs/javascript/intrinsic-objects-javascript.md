---
title: "내장 개체(JavaScript) | Microsoft Docs"
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
- built-in objects [JavaScript]
- intrinsic objects [JavaScript]
ms.assetid: 6520c634-a7d1-4a05-8c1b-2e79f449d2e4
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 242b572c2818f9968e6d5fc51e1272e3004c0f05
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="intrinsic-objects-javascript"></a>내장 개체(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 내장(또는 "기본 제공") 개체를 제공합니다. `Array`, `Boolean`, `Date`, `Error`, `Function`, **Global**, **JSON**, **Math**, **Number**, `Object`, `RegExp` 및 `String` 개체입니다. 내장 개체에는 [언어 참조](../javascript/reference/javascript-reference.md)에서 자세히 설명하는 연결된 메서드, 함수, 속성 및 상수가 있습니다.  
  
## <a name="array-object"></a>Array 개체  
 배열 아래 첨자는 개체의 속성으로 간주될 수 있으며, 숫자 인덱스에서 참조됩니다. 배열에 추가된 명명된 속성은 숫자로 인덱싱할 수 없습니다. 배열 요소와 별개입니다.  
  
 새 배열을 만들려면 다음 예제와 같이 **new** 연산자 및 **Array()** [생성자](../javascript/reference/constructor-property-object-javascript.md)를 사용합니다.  
  
```JavaScript  
var theMonths = new Array(12);  
theMonths[0] = "Jan";  
theMonths[1] = "Feb";  
theMonths[2] = "Mar";  
theMonths[3] = "Apr";  
theMonths[4] = "May";  
theMonths[5] = "Jun";  
theMonths[6] = "Jul";  
theMonths[7] = "Aug";  
theMonths[8] = "Sep";  
theMonths[9] = "Oct";  
theMonths[10] = "Nov";  
theMonths[11] = "Dec";  
```  
  
 `Array` 키워드를 사용하여 배열을 만드는 경우 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 항목 수를 기록하는 **length** 속성을 포함합니다. 숫자를 지정하지 않으면 길이가 0으로 설정되고 배열에 항목이 없습니다. 숫자를 지정하면 길이가 해당 숫자로 설정됩니다. 매개 변수를 두 개 이상 지정하면 매개 변수가 배열의 항목으로 사용됩니다. 또한 매개 변수 개수가 다음 예제와 같이 length 속성에 할당되며, 이는 앞의 예제와 같습니다.  
  
```JavaScript  
var theMonths = new Array("Jan", "Feb", "Mar", "Apr", "May", "Jun",   
"Jul", "Aug", "Sep", "Oct", "Nov", "Dec");  
```  
  
 `Array` 키워드를 사용하여 만든 배열에 요소를 추가하면 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 **length**의 값을 자동으로 변경합니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 배열 인덱스는 항상 1이 아니라 0부터 시작하므로 length 속성은 항상 배열에서 가장 큰 인덱스보다 1이 더 큽니다.  
  
## <a name="string-object"></a>String 개체  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 문자열(및 숫자)를 개체인 것처럼 처리할 수 있습니다. [string 개체](../javascript/reference/string-object-javascript.md)에는 문자열에 사용할 수 있는 특정 기본 제공 메서드가 있습니다. 그 중 하나는 문자열의 일부를 반환하는 [substring 메서드](../javascript/reference/substring-method-string-javascript.md)입니다. 두 개의 숫자를 해당 인수로 사용합니다.  
  
```JavaScript  
var aString = "0123456789";  
  
// This code sets aChunk to "456".  
var aChunk = aString.substring(4, 7);  
  
// This code sets anotherChunk to "456", using  
// the lower value index as the starting index.  
var anotherChunk = aString.substring(7, 4);  
  
// This code sets the firstLetter variable to "J"  
// by using the array in the preceding array creation example.  
firstLetter = theMonths[5].substring(0,1);  
```  
  
 `String` 개체의 다른 속성은 **length** 속성입니다. 이 속성은 문자열의 문자 수(빈 문자열의 경우 0)를 포함합니다. 숫자 값이며, 계산에 직접 사용할 수 있습니다.  
  
```JavaScript  
var howLong = "Hello World".length  // Sets the howLong variable to 11.  
```  
  
## <a name="math-object"></a>Math 개체  
 **Math** 개체에는 미리 정의된 많은 상수 및 함수가 포함됩니다. 상수는 특정 숫자입니다. 이러한 특정 숫자 중 하나는 pi 값(약 3.14159...)입니다. 이 숫자는 다음 예제에 표시된 **Math.PI** 상수입니다.  
  
```JavaScript  
var radius = 5;  
var circleArea = Math.PI * radius * radius;  
```  
  
 **Math** 개체의 기본 제공 함수 중 하나는 지수 메서드, 즉 숫자의 지정된 거듭제곱을 구하는 `Math.pow`입니다. 다음 예제에서는 pi와 지수를 둘 다 사용하여 구의 부피를 계산합니다.  
  
```JavaScript  
var volume = (4/3)*(Math.PI*Math.pow(radius,3));  
```  
  
## <a name="date-object"></a>Date 개체  
 `Date` 개체를 사용하여 임의의 날짜 및 시간을 나타내고, 현재 시스템 날짜를 가져오고, 날짜 간의 차이를 계산할 수 있습니다. 모두 미리 정의된 여러 속성 및 메서드가 있습니다. 일반적으로 `Date` 개체는 요일, 월, 일 및 연도, 시간의 시, 분 및 초를 제공합니다. 이 정보는 1970년 1월 1일 00:00:00.000 GMT 이후의 밀리초 수를 기반으로 합니다. GMT는 그리니치 표준시의 약어로, 세계 시간 표준에서 실행된 신호를 참조하는 UTC 또는 "협정 세계시"라는 용어를 사용하는 것이 좋습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 대략 250,000 B.C.에서 255,000 A.D. 범위에 있는 날짜를 처리할 수 있습니다.  
  
 새 `Date` 개체를 만들려면 다음 예제와 같이 **new** 연산자를 사용합니다.  
  
```JavaScript  
var toDay = new Date();    
var thisYear = toDay.getFullYear();  
var thisMonth = theMonths[toDay.getMonth()];  
var thisDay = thisMonth  + " " + toDay.getDate() + ", " + thisYear;  
```  
  
## <a name="number-object"></a>Number 개체  
 **Math** 개체에서 사용할 수 있는 특수 숫자 상수(예: `PI`) 외에도 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 **Number** 개체를 통해 다른 여러 상수를 사용할 수 있습니다.  
  
|상수|설명|  
|--------------|-----------------|  
|Number.MAX_VALUE|가능한 최대값으로, 약 1.79E+308입니다. 양수 또는 음수일 수 있습니다. 시스템마다 값이 약간 다릅니다.|  
|Number.MIN_VALUE|가능한 최소값으로, 약 5.00E-324입니다. 양수 또는 음수일 수 있습니다. 시스템마다 값이 약간 다릅니다.|  
|Number.NaN|숫자가 아닌 특수 값입니다. "숫자가 아닙니다."|  
|Number.POSITIVE_INFINITY|가장 큰 양수(Number.MAX_VALUE)보다 큰 양수 값은 자동으로 이 값으로 변환됩니다. 무한대로 표시됩니다.|  
|Number.NEGATIVE_INFINITY|가장 큰 음수(-Number.MAX_VALUE)보다 큰 음수 값은 자동으로 이 값으로 변환됩니다. -무한대로 표시됩니다.|  
  
 **Number.NaN**은 "숫자가 아님"으로 정의되는 특수 상수입니다. 숫자로 구문 분석할 수 없는 문자열을 구문 분석하려고 하면 **Number.NaN**이 반환됩니다. `NaN`은 모든 숫자 및 자신과 같지 않습니다. `NaN` 결과를 테스트하려면 **Number.NaN**과 비교하지 말고 **isNaN()** 함수를 사용합니다.  
  
## <a name="json-object"></a>JSON 개체  
 JSON은 JavaScript 언어의 개체 리터럴 표기법 하위 집합을 기반으로 하는 경량 데이터 교환 형식입니다.  
  
 JSON 개체는 JSON 텍스트 형식과의 변환에 사용되는 두 개의 함수를 제공합니다. [JSON.stringify](../javascript/reference/json-stringify-function-javascript.md) 함수는 개체와 배열을 JSON 텍스트로 직렬화합니다. [JSON.parse](../javascript/reference/json-parse-function-javascript.md) 함수는 JSON 텍스트를 역직렬화하여 메모리 내 개체를 생성합니다. 자세한 내용은 [JavaScript 및 .NET의 JSON(JavaScript Object Notation) 소개](http://go.microsoft.com/fwlink/?LinkId=124098)를 참조하세요.  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 개체](../javascript/reference/javascript-objects.md)
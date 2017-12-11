---
title: "날짜 및 시간 문자열(JavaScript) | Microsoft Docs"
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
ms.assetid: ba0798c5-3574-4434-89f4-3d90be276001
caps.latest.revision: "47"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6218ba273b26243382d1e825b6da961d604917ab
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="date-and-time-strings-javascript"></a>날짜 및 시간 문자열(JavaScript)
여러 가지 기법을 사용하여 JavaScript 날짜 및 시간 문자열을 지정하고 형식을 지정할 수 있습니다.  
  
## <a name="formatting-dates-using-intldatetimeformat"></a>Intl.DateTimeFormat를 사용하여 날짜 형식 지정  
 Internet Explorer 11에서는 [ECMAScript 국제화 API 사양](http://www.ecma-international.org/ecma-402/1.0/) 중 하나인 [Intl.DateTimeFormat 개체](../javascript/reference/intl-datetimeformat-object-javascript.md)에 대한 지원을 소개합니다. 날짜 서식을 지정하려면 직접 이 개체를 사용하거나 [toLocaleDateString 메서드(Date)](../javascript/reference/tolocaledatestring-method-date-javascript.md) 및 [toLocaleTimeString 메서드(Date)](../javascript/reference/tolocaletimestring-method-date-javascript.md)의 업데이트된 구현을 사용할 수 있습니다. 이러한 [Date 개체](../javascript/reference/date-object-javascript.md) 메서드는 `Intl.DateTimeFormat`을 내부적으로 사용하여 로캘 및 다른 형식 지정 옵션에 대한 새로운 선택적 매개 변수를 지원합니다.  
  
 다음 예제에서는 날짜 및 시간 형식을 지정하기 위해 `toLocaleDateString` 및 `toLocaleTimeString`을 사용하는 방법을 보여 줍니다. 이 메서드로 전달되는 첫 번째 매개 변수는 "en-us"와 같은 로캘 값입니다. 나타나는 두 번째 매개 변수는 요일에 대한 긴 형식 같은 형식 지정 옵션을 지정합니다.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = {  
    weekday: "long", year: "numeric", month: "short",  
    day: "numeric", hour: "2-digit", minute: "2-digit"  
};  
  
document.write(date.toLocaleDateString("en-US"));  
document.write(date.toLocaleTimeString("en-us", options));  
document.write(date.toLocaleDateString("ja-JP"));  
document.write(date.toLocaleTimeString("ja-JP", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013  
// ‎Friday‎, ‎Feb‎ ‎1‎, ‎2013‎ ‎06‎:‎00‎ ‎AM  
// ‎2013‎年‎2‎月‎1‎日‎  
// ‎2013‎年‎2‎月‎1‎日 ‎金曜日‎ ‎06‎:‎00  
```  
  
 형식 지정 옵션의 전체 목록은 [Intl.DateTimeFormat 개체](../javascript/reference/intl-datetimeformat-object-javascript.md)를 참조하세요.  
  
## <a name="formatting-dates"></a>날짜 형식 지정  
 Internet Explorer 11 이전의 JavaScript에는 날짜 및 시간 형식을 지정할 특정 메서드가 없습니다. 이전 브라우저 버전에 고유한 날짜 형식 지정을 제공하려면 [getDay 메서드(Date)](../javascript/reference/getday-method-date-javascript.md), [getDate 메서드(Date)](../javascript/reference/getdate-method-date-javascript.md), [getMonth 메서드(Date)](../javascript/reference/getmonth-method-date-javascript.md) 및 [getFullYear 메서드(Date)](../javascript/reference/getfullyear-method-date-javascript.md)를 사용합니다. ([getYear 메서드(Date)](../javascript/reference/getyear-method-date-javascript.md)는 더 이상 사용되지 않으며 사용해서는 안 됩니다.)  
  
```JavaScript  
var myDate = new Date("February 3, 2001");  
var myDate = new Date("February 3 2001");  
document.write((myDate.getMonth() + 1) + "-" + myDate.getDate() + "-" + myDate.getFullYear());  
document.write("<br/>");  
document.write((myDate.getMonth() + 1) + "/" + myDate.getDate() + "/" + myDate.getFullYear());  
  
//Output:  
// 2-3-2001  
// 2/3/2001  
```  
  
 [getHours 메서드(Date)](../javascript/reference/gethours-method-date-javascript.md), [getMinutes 메서드(Date)](../javascript/reference/getminutes-method-date-javascript.md), [getSeconds 메서드(Date)](../javascript/reference/getseconds-method-date-javascript.md) 및 [getMilliseconds 메서드(Date)](../javascript/reference/getmilliseconds-method-date-javascript.md)를 사용하여 사용자 고유의 형식 지정을 제공할 수 있습니다.  
  
```JavaScript  
myDate = new Date();  
myDate.setHours(10, 30, 53, 400);  
  
document.write(myDate.getHours() + ":" + myDate.getMinutes() + ":" + myDate.getSeconds() +   
":" + myDate.getMilliseconds());  
  
// Output:   
// 10:30:53:400  
```  
  
## <a name="converting-strings-to-dates"></a>문자열을 날짜로 변환  
 `Date` 또는 `Date(dateStr)`를 사용하여 `Date.parse(dateStr)` 개체를 구성하는 문자열을 지정할 수 있습니다. JavaScript에서는 다음 규칙을 사용하여 날짜 문자열을 구문 분석합니다.  
  
-   먼저 [ISO 날짜 형식](#ISO)을 사용하여 날짜 문자열의 구문 분석을 시도합니다.  
  
    > [!NOTE]
    >  JavaScript는 ISO 8601 확장 형식의 단순화된 버전을 사용합니다.  
  
-   날짜 문자열이 ISO 형식이 아닌 경우 JavaScript는 [다른 날짜 형식](#OtherDateFormats)을 사용하여 날짜 구문 분석을 시도합니다.  
  
<a name="ISO"></a>   
## <a name="iso-date-format"></a>ISO 날짜 형식  
 ISO 형식은 ISO 8601 확장 형식의 단순화된 버전입니다. 형식은 다음과 같습니다.  
  
 `YYYY-MM-DDTHH:mm:ss.sssZ`  
  
> [!IMPORTANT]
>  Internet Explorer 8 표준 모드 및 특수 모드에서는 ISO 날짜 형식이 지원되지 않습니다.  
  
 다음 표에서는 이 형식의 각 부분에 대해 설명합니다.  
  
|기호|설명|값|  
|------------|-----------------|------------|  
|`-`, `:`, `.`, `T`|문자열에 실제로 있는 문자입니다. `T`는 시작 시간을 지정합니다.||  
|`YYYY`|연도입니다. 4자리 연도 대신 확장 연도를 사용할 수 있습니다. 자세한 내용은 이 항목의 뒷부분에 나오는 [확장 연도](../javascript/date-and-time-strings-javascript.md#bkmk_extend)를 참조하세요.||  
|`MM`|월|01 ~ 12|  
|`DD`|일|01 ~ 31|  
|`HH`|시|00 ~ 24|  
|`mm`|분|00 ~ 59|  
|`ss`|초. 시간이 지정된 경우 초 및 밀리초는 선택 사항입니다.|00 ~ 59|  
|`sss`|밀리초|00 ~ 999|  
|`Z`|이 위치의 값은 다음 중 하나일 수 있습니다. 값을 생략하면 UTC 시간이 사용됩니다.<br /><br /> -   `Z`는 UTC 시간을 나타냅니다.<br />-   `+hh:mm`은 입력 시간이 UTC 시간 이후에 지정된 오프셋 시간임을 나타냅니다.<br />-   `-hh:mm`은 입력 시간이 UTC 시간 이전에 지정된 오프셋 시간의 절대값임을 나타냅니다.||  
  
 문자열은 `YYYY`, `YYYY-MM`, `YYYY-MM-DD` 형식의 날짜만 포함할 수 있습니다.  
  
 ISO 형식은 표준 시간대 이름을 지원하지 않습니다. `Z` 위치를 사용하여 UTC 시간의 오프셋 값을 지정할 수 있습니다. `Z` 위치에 값을 포함하지 않으면 UTC 시간이 사용됩니다.  
  
 자정은 00:00을 사용하거나 이전 날짜의 경우 24:00을 사용하여 지정할 수 있습니다. 2010-05-25T00:00 및 2010-05-24T24:00의 두 문자열은 같은 시간을 지정합니다.  
  
 ISO 형식으로 날짜를 반환하려면 [toISOString 메서드(Date)](../javascript/reference/toisostring-method-date-javascript.md)를 사용하면 됩니다.  
  
<a name="bkmk_extend"></a>   
### <a name="extended-years"></a>확장 연도  
 *확장 연도*는 4자리 숫자 대신 6자리 숫자를 포함하며 플러스 또는 마이너스 기호가 접두사로 붙습니다. 예를 들어, `+002010` 확장 연도는 `2010`과 동일합니다. 확장 연도를 사용하면 0년 이전 또는 9999년 이후의 연도를 표시할 수 있습니다.  
  
 6자리 형식을 사용할 경우 플러스 또는 마이너스 기호를 사용해야 합니다. 4자리 형식을 사용할 경우 기호가 없어야 합니다. 따라서 `0000` 및 `+000000`은 허용되지만 `000000` 및`-0001`은 오류가 발생합니다. 확장 연도 0은 양수로 간주되므로 플러스 기호가 접두사로 붙습니다.  
  
 [toISOString 메서드(Date)](../javascript/reference/toisostring-method-date-javascript.md)는 항상 0년 이전 및 9999년 이후의 연도에 대해 확장 연도 형식을 사용합니다.  
  
> [!NOTE]
>  [!INCLUDE[jsv9](../javascript/includes/jsv9-md.md)]  
  
<a name="OtherDateFormats"></a>   
## <a name="other-date-formats"></a>기타 날짜 형식  
 날짜 문자열이 ISO 형식이 아닌 경우 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 다음과 같은 규칙을 사용하여 구문 분석합니다.  
  
 간단한 날짜  
  
-   형식은 연도/월/일(예: 2010/06/08)을 따라야 합니다.  
  
-   "/" 또는 "-"를 구분 기호로 사용할 수 있습니다.  
  
 자세한 날짜  
  
-   연도, 월 및 일을 임의 순서로 표시할 수 있습니다. "6월 8일 2010년" 및 "2010년 6월 8일" 모두 유효합니다.  
  
-   연도는 두 자리 또는 네 자리 숫자일 수 있습니다. 연도에 두 자리 숫자만 포함된 경우 최소한 70 이상이어야 합니다.  
  
-   월과 일 이름은 최소 두 글자 이상이어야 합니다. 고유하지 않은 두 개 문자 이름은 제일 마지막에 일치되는 이름으로 확인됩니다. 예를 들어, "Ju"는 June이 아닌 July를 지정합니다.  
  
-   요일은 지정된 날짜의 나머지 부분과 일치하지 않을 경우 무시됩니다. 예를 들어, "1996년 11월 9일 화요일"은 해당 날짜의 요일을 확인했을 때 금요일이 올바르기 때문에 "1996년 11월 9일 금요일"로 분석됩니다.  
  
 시간  
  
-   시, 분 및 초는 콜론으로 구분됩니다. 하지만 시간 중 일부 요소를 생략할 수 있습니다. "10:", "10:11" 및 "10:11:12"는 모두 유효합니다.  
  
-   PM이 지정되었고 지정된 시간이 최소 13 이상이면 NaN이 반환됩니다. 예를 들어 "23:15 PM"은 NaN을 반환합니다.  
  
 일반  
  
-   잘못된 날짜가 포함된 문자열은 NaN을 반환합니다. 예를 들어, 두 개의 연도나 두 개의 월이 포함된 문자열은 NaN을 반환합니다.  
  
-   [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 모든 표준 시간대, UTC(협정 세계 표준시) 및 GMT(그리니치 표준시)를 지원합니다. ISO 형식은 표준 시간대를 지원하지 않습니다.  
  
-   괄호로 묶인 텍스트는 주석으로 처리됩니다. 괄호는 중첩될 수 있습니다.  
  
-   쉼표와 공백은 구분 기호로 처리됩니다. 여러 개의 구분 기호를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 서로 다른 날짜 및 시간 문자열을 구문 분석한 결과를 보여 줍니다.  
  
```  
document.writeln((new Date("2010")).toUTCString());   
  
document.writeln((new Date("2010-06")).toUTCString());  
  
document.writeln((new Date("2010-06-09")).toUTCString());  
  
 // Specifies Z, which indicates UTC time.  
document.writeln((new Date("2010-06-09T15:20:00Z")).toUTCString());  
  
 // Specifies -07:00 offset, which is equivalent to Pacific Daylight time.  
document.writeln((new Date("2010-06-09T15:20:00-07:00")).toGMTString());  
  
// Specifies a non-ISO Long date.  
document.writeln((new Date("June 9, 2010")).toUTCString());  
  
// Specifies a non-ISO Long date.  
document.writeln((new Date("2010 June 9")).toUTCString());  
  
// Specifies a non-ISO Short date and time.  
document.writeln((new Date("6/9/2010 3:20 pm")).toUTCString());  
  
// Output:  
// Fri, 1 Jan 2010 00:00:00 UTC  
// Tue, 1 Jun 2010 00:00:00 UTC  
// Wed, 9 Jun 2010 00:00:00 UTC  
// Wed, 9 Jun 2010 15:20:00 UTC  
// Wed, 9 Jun 2010 22:20:00 UTC  
// Wed, 9 Jun 2010 07:00:00 UTC  
// Wed, 9 Jun 2010 07:00:00 UTC  
// Wed, 9 Jun 2010 22:20:00 UTC  
```  
  
 현지 시간이 지정된 경우 표준 시간대에 따라 결과가 달라질 수 있습니다.  
  
> [!IMPORTANT]
>  Internet Explorer 8 표준 모드 및 특수 모드에서는 ISO 날짜 형식이 지원되지 않습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Date 개체](../javascript/reference/date-object-javascript.md)   
 [Date.parse 함수](../javascript/reference/date-parse-function-javascript.md)
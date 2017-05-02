---
title: "Date 개체(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Date"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "날짜, 확인"
ms.assetid: ce2202bb-7ec9-4f5a-bf48-3a04feff283e
caps.latest.revision: 29
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 29
---
# Date 개체(JavaScript)
날짜와 시간의 기본적인 저장 및 검색을 가능하게 합니다.  
  
## 구문  
  
```  
  
      dateObj = new Date()  
dateObj = new Date(dateVal)  
dateObj = new Date(year, month, date[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  `Date` 개체가 할당되는 변수 이름입니다.  
  
 `dateVal`  
 필수 요소.  숫자값 `dateVal`이 UTC\(Universal Coordinated Time\)로 지정된 날짜와 1970년 1월 1일 자정 사이의 시간을 밀리초로 나타냅니다.  문자열인 경우 `dateVal`이 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)의 규칙에 따라 구문 분석됩니다.  `dateVal` 인수는 ActiveX 개체에서 반환된 VT\_DATE 값일 수도 있습니다.  
  
 `year`  
 필수 요소.  예를 들어 76이 아니라 1976처럼 전체 연도로 나타냅니다.  
  
 `month`  
 필수 요소.  월은 0부터 11까지의 정수\(1월부터 12월\)로 나타냅니다.  
  
 `date`  
 필수 요소.  날짜는 1부터 31까지의 정수로 나타냅니다.  
  
 `hours`  
 선택 사항입니다.  `minutes`를 사용하면 반드시 사용해야 합니다.  시간은 0부터 23까지\(자정부터 오후 11시\)의 정수로 나타냅니다.  
  
 minutes  
 선택 사항입니다.  `seconds`를 사용하면 반드시 사용해야 합니다.  분은 0부터 59까지의 정수로 나타냅니다.  
  
 `seconds`  
 선택 사항입니다.  `milliseconds`를 사용하면 반드시 사용해야 합니다.  초는 0부터 59까지의 정수로 나타냅니다.  
  
 `ms`  
 선택 사항입니다.  밀리초는 0부터 999까지의 정수로 나타냅니다.  
  
## 설명  
 `Date` 개체에는 밀리초 단위까지 특정 인스턴스를 시간으로 나타내는 숫자가 포함되어 있습니다.  인수 값이 정해진 인수 값의 범위보다 크거나 음수이면 저장된 다른 값은 그에 따라 자동적으로 수정됩니다.  예를 들어 150초로 지정하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 2분 30초로 다시 정의합니다.  
  
 숫자가 `NaN`이면 개체가 시간의 특정 인스턴트를 나타내지 않습니다.  `Date` 개체에 매개 변수를 전달하지 않으면 현재 시간\(UTC\)으로 초기화됩니다.  개체에 값을 지정해야 사용할 수 있습니다.  
  
 `Date` 개체에서 나타낼 수 있는 날짜 범위는 1970년 1월 1일 전후로 약 285,616년입니다.  
  
 `Date` 개체 사용 방법과 관련 메서드에 대한 자세한 내용은 [날짜 및 시간 계산\(JavaScript\)](../../javascript/calculating-dates-and-times-javascript.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 `Date` 개체를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var dateString = "Today's date is: ";  
  
var newDate = new Date();  
  
// Get the month, day, and year.  
dateString += (newDate.getMonth() + 1) + "/";  
dateString += newDate.getDate() + "/";  
dateString += newDate.getFullYear();  
  
document.write(dateString);  
  
// Output: Today's date is: <date>  
```  
  
## 요구 사항  
 `Date object`는 [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]에서 도입되었습니다.  다음 목록의 일부 멤버는 이후 버전에서 도입되었습니다.  자세한 내용은 [버전 정보](../../javascript/reference/javascript-version-information.md) 또는 개별 멤버에 대한 설명서를 참조하십시오.  
  
## 속성  
 다음 표에서는 `Date Object`의 속성을 나열합니다.  
  
|속성|설명|  
|--------|--------|  
|[constructor 속성](../../javascript/reference/constructor-property-date.md)|개체를 만드는 함수를 지정합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-date.md)|개체 클래스의 프로토타입에 대한 참조를 반환합니다.|  
  
## 기능  
 다음 표에서는 `Date Object`의 함수를 나열합니다.  
  
|기능|설명|  
|--------|--------|  
|[Date.now 함수](../../javascript/reference/date-now-function-javascript.md)|1970년 1월 1일과 현재 날짜 및 시간 사이의 밀리초 값을 반환합니다.|  
|[Date.parse 함수](../../javascript/reference/date-parse-function-javascript.md)|날짜를 포함한 문자열 구문을 분석하여 1970년 1월 1일 자정부터 해당 날짜 사이의 시간을 밀리초로 반환합니다.|  
|[Date.UTC 함수](../../javascript/reference/date-utc-function-javascript.md)|UTC\(지역 표준시\) 또는 GMT\(그리니치 표준시\) 1970년 1월 1일 자정부터 주어진 날짜 사이의 시간을 밀리초로 반환합니다.|  
  
<a name="js56jsobjdatemeth"></a>   
## 메서드  
 다음 표에서는 `Date Object`의 메서드를 나열합니다.  
  
|방법|설명|  
|--------|--------|  
|[getDate 메서드](../../javascript/reference/getdate-method-date-javascript.md)|로컬 시간을 사용하여 일\(월 기준\) 값을 반환합니다.|  
|[getDay 메서드](../../javascript/reference/getday-method-date-javascript.md)|로컬 시간을 사용하여 일\(주 기준\) 값을 반환합니다.|  
|[getFullYear 메서드](../../javascript/reference/getfullyear-method-date-javascript.md)|로컬 시간을 사용하여 연도 값을 반환합니다.|  
|[getHours 메서드](../../javascript/reference/gethours-method-date-javascript.md)|로컬 시간을 사용하여 시간 값을 반환합니다.|  
|[getMilliseconds 메서드](../../javascript/reference/getmilliseconds-method-date-javascript.md)|로컬 시간을 사용하여 밀리초 값을 반환합니다.|  
|[getMinutes 메서드](../../javascript/reference/getminutes-method-date-javascript.md)|로컬 시간을 사용하여 분 값을 반환합니다.|  
|[getMonth 메서드](../../javascript/reference/getmonth-method-date-javascript.md)|로컬 시간을 사용하여 월 값을 반환합니다.|  
|[getSeconds 메서드](../../javascript/reference/getseconds-method-date-javascript.md)|로컬 시간을 사용하여 초 값을 반환합니다.|  
|[getTime 메서드](../../javascript/reference/gettime-method-date-javascript.md)|`Date` 개체의 시간 값을 1970년 1월 1일 자정 이후로 밀리초 단위로 반환합니다.|  
|[getTimezoneOffset 메서드](../../javascript/reference/gettimezoneoffset-method-date-javascript.md)|호스트 컴퓨터와 UTC\(지역 표준시\) 사이의 시간 차를 분으로 반환합니다.|  
|[getUTCDate 메서드](../../javascript/reference/getutcdate-method-date-javascript.md)|UTC를 사용하여 일\(월 기준\) 값을 반환합니다.|  
|[getUTCDay 메서드](../../javascript/reference/getutcday-method-date-javascript.md)|UTC를 사용하여 일\(주 기준\) 값을 반환합니다.|  
|[getUTCFullYear 메서드](../../javascript/reference/getutcfullyear-method-date-javascript.md)|UTC를 사용하여 연도 값을 반환합니다.|  
|[getUTCHours 메서드](../../javascript/reference/getutchours-method-date-javascript.md)|UTC를 사용하여 시간 값을 반환합니다.|  
|[getUTCMilliseconds 메서드](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)|UTC를 사용하여 밀리초 값을 반환합니다.|  
|[getUTCMinutes 메서드](../../javascript/reference/getutcminutes-method-date-javascript.md)|UTC를 사용하여 분 값을 반환합니다.|  
|[getUTCMonth 메서드](../../javascript/reference/getutcmonth-method-date-javascript.md)|UTC를 사용하여 월 값을 반환합니다.|  
|[getUTCSeconds 메서드](../../javascript/reference/getutcseconds-method-date-javascript.md)|UTC를 사용하여 초 값을 반환합니다.|  
|[getVarDate 메서드](../../javascript/reference/getvardate-method-date-javascript.md)|`Date` 개체의 VT\_DATE 값을 반환합니다.|  
|[getYear 메서드](../../javascript/reference/getyear-method-date-javascript.md)|연도 값을 반환합니다.|  
|[hasOwnProperty 메서드](../../javascript/reference/hasownproperty-method-object-javascript.md)|개체에 지정된 이름을 가진 속성이 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[isPrototypeOf 메서드](../../javascript/reference/isprototypeof-method-object-javascript.md)|개체가 다른 개체의 프로토타입 체인에 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[propertyIsEnumerable 메서드](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|지정된 속성이 개체의 일부인지와 열거할 수 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[setDate 메서드](../../javascript/reference/setdate-method-date-javascript.md)|로컬 시간을 사용하여 숫자로 된 날짜\(월 기준\)를 설정합니다.|  
|[setFullYear 메서드](../../javascript/reference/setfullyear-method-date-javascript.md)|로컬 시간을 사용하여 연도 값을 설정합니다.|  
|[setHours 메서드](../../javascript/reference/sethours-method-date-javascript.md)|로컬 시간을 사용하여 시간 값을 설정합니다.|  
|[setMilliseconds 메서드](../../javascript/reference/setmilliseconds-method-date-javascript.md)|로컬 시간을 사용하여 밀리초 값을 설정합니다.|  
|[setMinutes 메서드](../../javascript/reference/setminutes-method-date-javascript.md)|로컬 시간을 사용하여 분 값을 설정합니다.|  
|[setMonth 메서드](../../javascript/reference/setmonth-method-date-javascript.md)|로컬 시간을 사용하여 월 값을 설정합니다.|  
|[setSeconds 메서드](../../javascript/reference/setseconds-method-date-javascript.md)|로컬 시간을 사용하여 초 값을 설정합니다.|  
|[setTime 메서드](../../javascript/reference/settime-method-date-javascript.md)|`Date` 개체의 날짜와 시간 값을 설정합니다.|  
|[setUTCDate 메서드](../../javascript/reference/setutcdate-method-date-javascript.md)|UTC를 사용하여 숫자로 된 날짜\(월 기준\)를 설정합니다.|  
|[setUTCFullYear 메서드](../../javascript/reference/setutcfullyear-method-date-javascript.md)|UTC를 사용하여 연도 값을 설정합니다.|  
|[setUTCHours 메서드](../../javascript/reference/setutchours-method-date-javascript.md)|UTC를 사용하여 시간 값을 설정합니다.|  
|[setUTCMilliseconds 메서드](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)|UTC를 사용하여 밀리초 값을 설정합니다.|  
|[setUTCMinutes 메서드](../../javascript/reference/setutcminutes-method-date-javascript.md)|UTC를 사용하여 분 값을 설정합니다.|  
|[setUTCMonth 메서드](../../javascript/reference/setutcmonth-method-date-javascript.md)|UTC를 사용하여 월 값을 설정합니다.|  
|[setUTCSeconds 메서드](../../javascript/reference/setutcseconds-method-date-javascript.md)|UTC를 사용하여 초 값을 설정합니다.|  
|[setYear 메서드](../../javascript/reference/setyear-method-date-javascript.md)|로컬 시간을 사용하여 연도 값을 설정합니다.|  
|[toDateString 메서드](../../javascript/reference/todatestring-method-date-javascript.md)|날짜를 문자열 값으로 반환합니다.|  
|[toGMTString 메서드](../../javascript/reference/togmtstring-method-date-javascript.md)|GMT\(그리니치 표준시\)를 사용하여 문자열로 변환된 날짜를 반환합니다.|  
|[toISOString 메서드](../../javascript/reference/toisostring-method-date-javascript.md)|날짜를 ISO 형식의 문자열 값으로 반환합니다.|  
|[toJSON 메서드](../../javascript/reference/tojson-method-date-javascript.md)|JSON serialization 이전에 개체 형식의 날짜를 변환하는 데 사용됩니다.|  
|[toLocaleDateString 메서드](../../javascript/reference/tolocaledatestring-method-date-javascript.md)|호스트 환경의 현재 로캘에 해당하는 문자열 값으로 날짜를 반환합니다.|  
|[toLocaleString 메서드](../../javascript/reference/tolocalestring-date.md)|현재 로캘을 사용하여 문자열로 변환된 개체를 반환합니다.|  
|[toLocaleTimeString 메서드](../../javascript/reference/tolocaletimestring-method-date-javascript.md)|호스트 환경의 현재 로캘에 해당하는 문자열 값으로 시간을 반환합니다.|  
|[toString 메서드](../../javascript/reference/tostring-method-date.md)|개체를 나타내는 문자열을 반환합니다.|  
|[toTimeString 메서드](../../javascript/reference/totimestring-method-date-javascript.md)|시간을 문자열 값으로 반환합니다.|  
|[toUTCString 메서드](../../javascript/reference/toutcstring-method-date-javascript.md)|UTC를 사용하여 문자열로 변환된 날짜를 반환합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-date.md)|지정한 개체의 원시 값을 반환합니다.|  
  
## 참고 항목  
 [날짜 및 시간 계산\(JavaScript\)](../../javascript/calculating-dates-and-times-javascript.md)   
 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)
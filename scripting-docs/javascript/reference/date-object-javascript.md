---
title: "Date 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Date
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, determining
ms.assetid: ce2202bb-7ec9-4f5a-bf48-3a04feff283e
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eb5d53f3bddfeb3a3ed1ab36e2b4be822964eba5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="date-object-javascript"></a>Date 개체(JavaScript)
기본적인 날짜 및 시간 저장/검색 기능을 사용하도록 설정합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      dateObj = new Date()  
dateObj = new Date(dateVal)  
dateObj = new Date(year, month, date[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. `Date` 개체가 할당되는 변수 이름입니다.  
  
 `dateVal`  
 필수 요소. 숫자 값인 경우 `dateVal` 1970 년 1 월 1 일 자정 지정 된 날짜와 시간에서 1/1000의 수를 나타냅니다. 문자열인 경우 `dateVal` 은 규칙에 따라 구문 분석 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)합니다. `dateVal` 일부 ActiveX 개체에서 반환 된 인수는 VT_DATE 값 일 수도 있습니다.  
  
 `year`  
 필수 요소. 예를 들어 전체 연도로 1976 (및 하지 76).  
  
 `month`  
 필수 요소. 0과 11 (12 월 1 월) 사이의 정수 월입니다.  
  
 `date`  
 필수 요소. 1에서 31 사이의 정수 날짜입니다.  
  
 `hours`  
 선택 사항입니다. 경우에 제공 해야 `minutes` 를 제공 합니다. 하는 정수 0에서 23 (오후 11 시 자정) 시간을 지정 합니다.  
  
 분  
 선택 사항입니다. 경우에 제공 해야 `seconds` 를 제공 합니다. 분을 지정 하는 0부터 59 까지의 정수로 합니다.  
  
 `seconds`  
 선택 사항입니다. 경우에 제공 해야 `milliseconds` 를 제공 합니다. 초는 0부터 59 까지의 정수로 합니다.  
  
 `ms`  
 선택 사항입니다. 하는 정수 0에서 999 사이의 밀리초를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 A `Date` 개체에 특정 기간의 시작 시간을 밀리초를 나타내는 숫자가 포함 되어 있습니다. 인수 값의 범위 보다 크면 음수, 저장 된 다른 값도 수정 됩니다. 예를 들어 150 초로 지정 하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 다시 정의 합니다 2 분 30 초입니다.  
  
 숫자가 이면 `NaN`, 개체는 특정 시간 인스턴스에만 나타내지 않습니다. 매개 변수 없이 전달 하는 경우는 `Date` 개체를 현재 시간 (UTC)으로 초기화 됩니다. 값을 사용 하려면 먼저 개체에 부여 되어야 합니다.  
  
 로 나타낼 수 있는 날짜 범위는 `Date` 개체는 1970 년 1 월 1 일의 어느 쪽에 285616 년에 약 합니다.  
  
 참조 [시간과 날짜를 계산 (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md) 사용 하는 방법에 대 한 자세한 내용은 `Date` 개체와 관련 된 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Date` 개체를 사용하는 방법을 보여줍니다.  
  
```JavaScript  
var dateString = "Today's date is: ";  
  
var newDate = new Date();  
  
// Get the month, day, and year.  
dateString += (newDate.getMonth() + 1) + "/";  
dateString += newDate.getDate() + "/";  
dateString += newDate.getFullYear();  
  
document.write(dateString);  
  
// Output: Today's date is: <date>  
```  
  
## <a name="requirements"></a>요구 사항  
 `Date object`는 [!INCLUDE[jsv1text](../../javascript/reference/includes/jsv1text-md.md)]에서 도입되었습니다. 다음 목록의 일부 멤버는 이후 버전에서 도입되었습니다. 자세한 내용은 참조 [버전 정보](../../javascript/reference/javascript-version-information.md) 또는 개별 멤버에 대 한 설명서입니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Date Object`의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[constructor 속성](../../javascript/reference/constructor-property-date.md)|개체를 만드는 함수를 지정합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-date.md)|개체 클래스의 프로토타입에 대한 참조를 반환합니다.|  
  
## <a name="functions"></a>함수  
 다음 표에서는 `Date Object`의 함수를 보여줍니다.  
  
|함수|설명|  
|---------------|-----------------|  
|[Date.now 함수](../../javascript/reference/date-now-function-javascript.md)|1970 년 1 월 1 일 사이의 밀리초 수를 반환 합니다. 현재 날짜 및 시간입니다.|  
|[Date.parse 함수](../../javascript/reference/date-parse-function-javascript.md)|날짜를 포함 하는 문자열을 구문 분석 하 고 해당 날짜 사이의 1970 년 1 월 1 일 자정 (밀리초)을 반환 합니다.|  
|[Date.UTC 함수](../../javascript/reference/date-utc-function-javascript.md)|1970 년 1 월 1 일 자정 사이의 밀리초 수를 반환 utc (협정 세계시) 또는 GMT () 및 제공 된 날짜입니다.|  
  
<a name="js56jsobjdatemeth"></a>   
## <a name="methods"></a>메서드  
 다음 표에서는 `Date Object`의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[getDate 메서드](../../javascript/reference/getdate-method-date-javascript.md)|현지 시간을 사용 하 여 일의 월을 반환 합니다.|  
|[getDay 메서드](../../javascript/reference/getday-method-date-javascript.md)|현지 시간을 사용 하 여 주 일 값을 반환 합니다.|  
|[getFullYear 메서드](../../javascript/reference/getfullyear-method-date-javascript.md)|현지 시간을 사용 하 여 년 값을 반환 합니다.|  
|[getHours 메서드](../../javascript/reference/gethours-method-date-javascript.md)|현지 시간을 사용 하 여 시간을 반환 합니다.|  
|[getMilliseconds 메서드](../../javascript/reference/getmilliseconds-method-date-javascript.md)|현지 시간을 사용 하 여 밀리초 값을 반환 합니다.|  
|[getMinutes 메서드](../../javascript/reference/getminutes-method-date-javascript.md)|현지 시간을 사용 하 여 분 값을 반환 합니다.|  
|[getMonth 메서드](../../javascript/reference/getmonth-method-date-javascript.md)|현지 시간을 사용 하 여 월 값을 반환 합니다.|  
|[getSeconds 메서드](../../javascript/reference/getseconds-method-date-javascript.md)|현지 시간을 사용 하 여 초 값을 반환 합니다.|  
|[getTime 메서드](../../javascript/reference/gettime-method-date-javascript.md)|시간 값을 반환는 `Date` 1970 년 1 월 1 일 자정 이후의 밀리초 수로 개체입니다.|  
|[getTimezoneOffset 메서드](../../javascript/reference/gettimezoneoffset-method-date-javascript.md)|호스트 컴퓨터에서 시간과 utc (협정 세계시) 사이의 차이 (분)을 반환합니다.|  
|[getUTCDate 메서드](../../javascript/reference/getutcdate-method-date-javascript.md)|UTC를 사용 하 여 일 월 값을 반환 합니다.|  
|[getUTCDay 메서드](../../javascript/reference/getutcday-method-date-javascript.md)|UTC를 사용 하 여 주 일 값을 반환 합니다.|  
|[getUTCFullYear 메서드](../../javascript/reference/getutcfullyear-method-date-javascript.md)|UTC를 사용 하 여 년 값을 반환 합니다.|  
|[getUTCHours 메서드](../../javascript/reference/getutchours-method-date-javascript.md)|UTC를 사용 하 여 시간 값을 반환 합니다.|  
|[getUTCMilliseconds 메서드](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)|UTC를 사용 하 여 밀리초 값을 반환 합니다.|  
|[getUTCMinutes 메서드](../../javascript/reference/getutcminutes-method-date-javascript.md)|UTC를 사용 하 여 분 값을 반환 합니다.|  
|[getUTCMonth 메서드](../../javascript/reference/getutcmonth-method-date-javascript.md)|UTC를 사용 하 여 월 값을 반환 합니다.|  
|[getUTCSeconds 메서드](../../javascript/reference/getutcseconds-method-date-javascript.md)|초 UTC를 사용 하는 값을 반환 합니다.|  
|[getVarDate 메서드](../../javascript/reference/getvardate-method-date-javascript.md)|VT_DATE 값을 반환는 `Date` 개체입니다.|  
|[getYear 메서드](../../javascript/reference/getyear-method-date-javascript.md)|연도 값을 반환 합니다.|  
|[hasOwnProperty 메서드](../../javascript/reference/hasownproperty-method-object-javascript.md)|개체에 지정된 이름을 가진 속성이 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[isPrototypeOf 메서드](../../javascript/reference/isprototypeof-method-object-javascript.md)|개체가 다른 개체의 프로토타입 체인에 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[propertyIsEnumerable 메서드](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|지정된 속성이 개체의 일부인지 여부 및 열거 가능한지 여부를 나타내는 부울 값을 반환합니다.|  
|[setDate 메서드](../../javascript/reference/setdate-method-date-javascript.md)|현지 시간을 사용 하 여 날짜를 설정 합니다.|  
|[setFullYear 메서드](../../javascript/reference/setfullyear-method-date-javascript.md)|현지 시간을 사용 하 여 년 값을 설정 합니다.|  
|[setHours 메서드](../../javascript/reference/sethours-method-date-javascript.md)|현지 시간을 사용 하 여 시간 값을 설정 합니다.|  
|[setMilliseconds 메서드](../../javascript/reference/setmilliseconds-method-date-javascript.md)|현지 시간을 사용 하 여 밀리초 값을 설정 합니다.|  
|[setMinutes 메서드](../../javascript/reference/setminutes-method-date-javascript.md)|현지 시간을 사용 하 여 분 값을 설정 합니다.|  
|[setMonth 메서드](../../javascript/reference/setmonth-method-date-javascript.md)|현지 시간을 사용 하 여 월 값을 설정 합니다.|  
|[setSeconds 메서드](../../javascript/reference/setseconds-method-date-javascript.md)|초 현지 시간을 사용 하 여 값을 설정 합니다.|  
|[setTime 메서드](../../javascript/reference/settime-method-date-javascript.md)|날짜 및 시간 값을 설정의 `Date` 개체입니다.|  
|[setUTCDate 메서드](../../javascript/reference/setutcdate-method-date-javascript.md)|UTC를 사용 하 여 날짜를 설정 합니다.|  
|[setUTCFullYear 메서드](../../javascript/reference/setutcfullyear-method-date-javascript.md)|UTC를 사용 하 여 년 값을 설정 합니다.|  
|[setUTCHours 메서드](../../javascript/reference/setutchours-method-date-javascript.md)|UTC를 사용 하 여 시간 값을 설정 합니다.|  
|[setUTCMilliseconds 메서드](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)|UTC를 사용 하 여 밀리초 값을 설정 합니다.|  
|[setUTCMinutes 메서드](../../javascript/reference/setutcminutes-method-date-javascript.md)|UTC를 사용 하 여 분 값을 설정 합니다.|  
|[setUTCMonth 메서드](../../javascript/reference/setutcmonth-method-date-javascript.md)|UTC를 사용 하 여 월 값을 설정 합니다.|  
|[setUTCSeconds 메서드](../../javascript/reference/setutcseconds-method-date-javascript.md)|초 UTC를 사용 하는 값을 설정 합니다.|  
|[setYear 메서드](../../javascript/reference/setyear-method-date-javascript.md)|현지 시간을 사용 하 여 년 값을 설정 합니다.|  
|[toDateString 메서드](../../javascript/reference/todatestring-method-date-javascript.md)|문자열 값으로 날짜를 반환합니다.|  
|[toGMTString 메서드](../../javascript/reference/togmtstring-method-date-javascript.md)|(GMT) 그리니치 표준시를 사용 하 여 문자열로 변환 된 날짜를 반환 합니다.|  
|[toISOString 메서드](../../javascript/reference/toisostring-method-date-javascript.md)|ISO 형식으로 날짜를 문자열 값으로 반환합니다.|  
|[toJSON 메서드](../../javascript/reference/tojson-method-date-javascript.md)|개체 형식의 JSON serialization 하기 전에 데이터를 변환 하는 데 사용 합니다.|  
|[toLocaleDateString 메서드](../../javascript/reference/tolocaledatestring-method-date-javascript.md)|호스트 환경의 현재 로캘에 해당 하는 문자열 값으로 날짜를 반환합니다.|  
|[toLocaleString 메서드](../../javascript/reference/tolocalestring-date.md)|현재 로캘을 사용 하 여 문자열로 변환 된 개체를 반환 합니다.|  
|[toLocaleTimeString 메서드](../../javascript/reference/tolocaletimestring-method-date-javascript.md)|호스트 환경의 현재 로캘에 해당 하는 문자열 값으로 시간을 반환합니다.|  
|[toString 메서드](../../javascript/reference/tostring-method-date.md)|개체를 나타내는 문자열을 반환합니다.|  
|[toTimeString 메서드](../../javascript/reference/totimestring-method-date-javascript.md)|문자열 값으로 시간을 반환 합니다.|  
|[toUTCString 메서드](../../javascript/reference/toutcstring-method-date-javascript.md)|UTC를 사용 하 여 문자열로 변환 된 날짜를 반환 합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-date.md)|지정된 개체의 기본 값을 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [날짜 및 시간 계산 (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md)   
 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)
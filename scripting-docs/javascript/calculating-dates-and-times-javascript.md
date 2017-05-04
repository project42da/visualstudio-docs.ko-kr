---
title: "날짜 및 시간 계산(JavaScript) | Microsoft Docs"
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
  - "날짜 및 시간 산술 연산[JavaScript]"
  - "JavaScript, 날짜 및 시간"
  - "날짜 비교[JavaScript]"
  - "날짜 및 시간 계산[JavaScript]"
ms.assetid: ea976f78-d934-479b-9056-880390d8bddd
caps.latest.revision: 34
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 34
---
# 날짜 및 시간 계산(JavaScript)
[Date 개체](../javascript/reference/date-object-javascript.md)를 사용하여 날짜 비교 및 경과 시간 계산과 같은 일반적인 달력 및 시계 작업을 수행할 수 있습니다.  
  
## 날짜를 현재 날짜로 설정  
 날짜를 지정하지 않고 [Date 개체](../javascript/reference/date-object-javascript.md)의 인스턴스를 만드는 경우 이 인스턴스는 연도, 월, 일, 시, 분, 초 및 밀리초를 포함하는 현재 날짜와 시간을 나타내는 값을 반환합니다.  그런 다음 이 날짜 및 시간을 읽거나 수정할 수 있습니다.  
  
 다음 예제에서는 매개 변수를 사용하지 않고 날짜를 인스턴스화하고 *mm\-dd\-yy* 형식으로 표시하는 방법을 보여 줍니다.  
  
```javascript  
var dt = new Date();  
  
// Display the month, day, and year. getMonth() returns a 0-based number.  
var month = dt.getMonth()+1;  
var day = dt.getDate();  
var year = dt.getFullYear();  
document.write(month + '-' + day + '-' + year);  
  
// Output: current month, day, year  
```  
  
## 특정 날짜 설정  
 생성자에 날짜 문자열을 전달하여 특정 날짜를 설정할 수 있습니다.  
  
```javascript  
var dt = new Date('8/24/2009');  
document.write(dt);  
  
// Output: Mon Aug 24 00:00:00 PDT 2009  
  
```  
  
> [!IMPORTANT]
>  날짜 문자열에 표시되는 표준 시간대는 로컬 컴퓨터에서 설정된 표준 시간대에 해당합니다.  
>   
>  [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 매개 변수로 사용하는 문자열의 형식에 대해 유연합니다.  예를 들어 "8\-24\-2009", "August 24, 2009" 또는 "24 Aug 2009"를 입력할 수 있습니다.  
  
 또한 시간을 지정할 수도 있습니다.  다음 예제에서는 ISO 형식으로 날짜 및 시간을 지정하는 한 가지 방법을 보여 줍니다.  "Z"는 UTC 시간을 나타냅니다.  
  
```javascript  
var dt = new Date('2010-06-09T15:20:00Z');  
document.write(dt);  
document.write("<br />");  
document.write(dt.toISOString());  
  
// Output:  
// Wed Jun 09 2010 08:20:00 GMT-0700 (Pacific Daylight Time)  
// 2010-06-09T15:20:00.000Z  
```  
  
 ISO와 같은 날짜 형식에 대한 자세한 내용은 [날짜 및 시간 문자열](../javascript/date-and-time-strings-javascript.md)을 참조하십시오.  
  
 다음 예제에서는 시간을 지정하는 다른 방법을 보여 줍니다.  
  
```javascript  
var dtA = new Date('8/24/2009 14:52:10');  
  
// The parameters are year, month, day, hours, minutes, seconds.  
var dtB = new Date(2009, 7, 24, 14, 52, 10);  
document.write(dtA);  
document.write("<br/>");  
document.write(dtB);  
  
// Output:  
// Mon Aug 24 14:52:10 PDT 2009  
// Mon Aug 24 14:52:10 PDT 2009  
  
```  
  
## 일, 월 및 연도 더하기 및 빼기  
 `Date` 개체의 getX 및 setX 메서드를 사용하여 특정 날짜 및 시간을 설정할 수 있습니다.  
  
 다음 예제에서는 날짜를 전날로 설정하는 방법을 보여 줍니다.  필요한 경우에는 월 및 연도 값도 변경됩니다.  
  
```javascript  
var myDate = new Date("1/1/1990");  
var dayOfMonth = myDate.getDate();  
myDate.setDate(dayOfMonth - 1);  
  
document.write(myDate);  
  
// Output: Sun Dec 31 00:00:00 PST 1989  
```  
  
 다음 예제에서는 다음 달의 첫날에서 하루를 빼서 이 달의 마지막 날로 날짜를 설정합니다.  
  
> [!TIP]
>  월은 0\(1월\)에서 11\(12월\)까지 번호가 지정되고,  요일은 0\(일요일\)에서 6\(토요일\)까지 번호가 지정됩니다.  
  
```javascript  
var myDate = new Date("1/1/1990")  
myDate.setMonth(myDate.getMonth() + 1);  
  
myDate.setDate (myDate.getDate() - 1);  
  
document.write(myDate);  
  
// Output: Wed Jan 31 00:00:00 PST 1990  
  
```  
  
## 요일 사용  
 [getDay 메서드](../javascript/reference/getday-method-date-javascript.md)는 요일을 0\(일요일\)에서 6\(토요일\)까지의 숫자로 가져옵니다. 이 메서드는 1에서 31까지의 숫자로 월의 일을 가져오는 [getDate 메서드](../javascript/reference/getdate-method-date-javascript.md)와는 다릅니다.  
  
 다음 예제에서는 미국에서 11월의 네 번째 목요일인 추수 감사절의 날짜를 설정합니다.  이 스크립트에서는 현재 연도의 11월 1을 찾은 다음 첫 번째 목요일을 찾아 3주를 더합니다.  
  
```javascript  
var myDate = new Date();  
myDate.setHours(0, 0, 0, 0);  
  
myDate.setYear(2013);  
  
// Determine November 1.  
myDate.setDate(1);  
myDate.setMonth(10);  
  
// Find Thursday.  
var thursday = 4;  
while(myDate.getDay() != thursday) {  
    myDate.setDate(myDate.getDate() + 1);  
}  
  
// Add 3 weeks.  
myDate.setDate(myDate.getDate() + 21);  
  
document.write(myDate);  
  
// Output: Thu Nov 28 00:00:00 <time zone> 2013  
  
```  
  
## 경과된 시간 계산  
 [getTime 메서드](../javascript/reference/gettime-method-date-javascript.md)는 1970년 1월 1일 자정을 기준으로 경과된 시간\(밀리초\)을 반환합니다.  날짜가 이 날짜 이전이면 음수를 반환합니다.  
  
 [getTime 메서드](../javascript/reference/gettime-method-date-javascript.md)를 사용하여 경과된 시간을 계산하는 데 필요한 시작 시간과 종료 시간을 설정할 수 있습니다.  그러면 몇 초 정도의 짧은 시간이나 며칠에 달하는 긴 시간을 측정할 때 사용할 수 있습니다.  
  
 다음 예제에서는 경과된 시간\(초\)을 계산합니다.  [getTime 메서드](../javascript/reference/gettime-method-date-javascript.md)는 0일 이후 경과된 시간\(밀리초\)을 가져옵니다.  
  
```javascript  
var startTime = new Date('1/1/1990');  
var startMsec = startTime.getMilliseconds();  
startTime.setTime(5000000);  
var elapsed = (startTime.getTime() - startMsec) / 1000;   
document.write(elapsed);  
  
// Output: 5000  
  
```  
  
 관리가 더 용이한 단위를 사용하려면 [getTime 메서드](../javascript/reference/gettime-method-date-javascript.md)에서 제공하는 밀리초를 적절한 수로 나누면 됩니다.  예를 들어, 밀리초를 일 단위로 바꾸려면 밀리초 값을 86,400,000\(1000밀리초 x 60초 x 60분 x 24시간\)으로 나눕니다.  
  
 다음 예제에서는 지정한 연도의 첫날부터 경과된 시간을 보여 줍니다.  여기서는 나누기 연산을 통해 경과된 시간을 일, 시, 분 및 초 단위로 계산합니다.  일광 절약 시간은 반영되지 않습니다.  
  
```javascript  
// Set the unit values in milliseconds.  
var msecPerMinute = 1000 * 60;  
var msecPerHour = msecPerMinute * 60;  
var msecPerDay = msecPerHour * 24;  
  
// Set a date and get the milliseconds  
var date = new Date('6/15/1990');  
var dateMsec = date.getTime();  
  
// Set the date to January 1, at midnight, of the specified year.  
date.setMonth(0);  
date.setDate(1);  
date.setHours(0, 0, 0, 0);  
  
// Get the difference in milliseconds.  
var interval = dateMsec - date.getTime();  
  
// Calculate how many days the interval contains. Subtract that  
// many days from the interval to determine the remainder.  
var days = Math.floor(interval / msecPerDay );  
interval = interval - (days * msecPerDay );  
  
// Calculate the hours, minutes, and seconds.  
var hours = Math.floor(interval / msecPerHour );  
interval = interval - (hours * msecPerHour );  
  
var minutes = Math.floor(interval / msecPerMinute );  
interval = interval - (minutes * msecPerMinute );  
  
var seconds = Math.floor(interval / 1000 );  
  
// Display the result.  
document.write(days + " days, " + hours + " hours, " + minutes + " minutes, " + seconds + " seconds.");  
  
//Output: 164 days, 23 hours, 0 minutes, 0 seconds.  
```  
  
### 사용자의 나이 확인  
 다음 예제에서는 사용자의 생일을 사용하여 사용자의 나이를 햇수로 계산합니다.  여기서는 현재 연도에서 출생 연도를 뺀 다음, 현재 연도에서 생일이 아직 지나지 않았으면 1을 더 뺍니다.  
  
```javascript  
var birthday = new Date("8/1/1985");  
var today = new Date();  
var years = today.getFullYear() - birthday.getFullYear();  
  
// Reset birthday to the current year.  
birthday.setFullYear(today.getFullYear());  
  
// If the user's birthday has not occurred yet this year, subtract 1.  
if (today < birthday)  
{  
    years--;  
}  
document.write("You are " + years + " years old.");  
  
// Output: You are <number of years> years old.  
  
```  
  
## 날짜 비교  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 날짜를 비교할 때 `==` 연산자는 연산자 양쪽의 날짜가 동일한 개체를 참조하는 경우에만 `true`를 반환합니다.  따라서 별도의 두 `Date` 개체가 동일한 날짜로 설정된 경우 `date1 == date2`는 `false`를 반환합니다.  또한 날짜로만 설정되고 시간으로 설정되지 않은 `Date` 개체는 해당 날짜의 자정으로 초기화됩니다.  따라서 지정된 시간 없이 설정된 한 `Date`를 `Date.now`와 비교하는 경우 먼저 `Date`가 자정으로 설정된 다음 `Date.now`는 자정으로 설정되지 않습니다.  
  
 다음 예제에서는 현재 날짜가 지정한 날짜와 같은지, 이전인지 또는 이후인지를 확인합니다.  `todayAtMidn`에서 현재 날짜를 설정하기 위해 스크립트는 현재 연도, 월 및 일에 대해 `Date` 개체를 만듭니다.  
  
```javascript  
// Get the current date at midnight.  
var now = new Date();   
var todayAtMidn = new Date(now.getFullYear(), now.getMonth(), now.getDate());  
  
// Set specificDate to a specified date at midnight.  
var specificDate = new Date("9/21/2009");  
  
// Compare the two dates by comparing the millisecond  
// representations.  
if (todayAtMidn.getTime() == specificDate.getTime())  
{  
    document.write("Same");  
}  
else  
{  
    document.write("Different");  
}  
  
//Output: Different  
```  
  
 위의 예제를 수정하면 제공된 날짜가 특정 범위 안에 있는지 확인할 수 있습니다.  
  
```javascript  
// Get the current date at midnight.  
var now = new Date();  
var todayAtMidn = new Date(now.getFullYear(), now.getMonth(), now.getDate());  
  
// Set start/end dates to a specified date (ISO format).  
var startDate = new Date("2009-06-09T15:20:00Z");  
var endDate = new Date("2011-06-09T15:20:00Z");  
  
// Compare the two dates by comparing the millisecond  
// representations.  
if (todayAtMidn.getTime() > startDate.getTime() &&   
    todayAtMidn.getTime() < endDate.getTime()) {  
    document.write("Specified date is within this range.");  
}  
else {  
    document.write("Specified date is not in this range.");  
}  
  
// Output: Specified date is not in this range.  
```  
  
## 참고 항목  
 [Date 개체](../javascript/reference/date-object-javascript.md)
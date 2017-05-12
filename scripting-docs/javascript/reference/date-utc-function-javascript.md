---
title: "Date.UTC 함수(JavaScript) | Microsoft Docs"
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
  - "UTC"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "UTC 함수[JavaScript]"
  - "UTC 날짜, 반환"
  - "Date.UTC 함수[JavaScript]"
ms.assetid: c0d67ce1-a47e-4dfd-bbf4-21619c406a0f
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# Date.UTC 함수(JavaScript)
UTC\(협정 세계 표준시\)\(또는 GMT\) 1970년 1월 1일 자정부터 지정된 날짜 사이의 시간을 밀리초로 반환합니다.  
  
## 구문  
  
```  
Date.UTC(year, month, day[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## 매개 변수  
 `year`  
 필수 요소.  다른 세기의 날짜를 정확히 동시에 나타내기 위해 연도를 네 자리 숫자로 표기해야 합니다.  `year`에 0부터 99까지의 숫자가 사용되면 `year`는 1900 \+ `year`인 것으로 간주됩니다.  
  
 `month`  
 필수 요소.  월은 0부터 11까지의 정수\(1월부터 12월\)로 나타냅니다.  
  
 `day`  
 필수 요소.  날짜는 1부터 31까지의 정수로 나타냅니다.  
  
 `hours`  
 선택 사항입니다.  `minutes`를 사용하면 반드시 사용해야 합니다.  시간은 0부터 23까지\(자정부터 오후 11시\)의 정수로 나타냅니다.  
  
 `minutes`  
 선택 사항입니다.  `seconds`를 사용하면 반드시 사용해야 합니다.  분은 0부터 59까지의 정수로 나타냅니다.  
  
 `seconds`  
 선택 사항입니다.  `milliseconds`를 사용하면 반드시 사용해야 합니다.  초는 0부터 59까지의 정수로 나타냅니다.  
  
 `ms`  
 선택 사항입니다.  밀리초는 0부터 999까지의 정수로 나타냅니다.  
  
## 설명  
 `Date.UTC` 함수는 UTC 1970년 1월 1일 자정과 주어진 날짜 사이의 시간을 밀리초로 반환합니다.  이 반환 값은 `setTime` 메서드와 `Date` 개체 생성자에서 사용할 수 있습니다.  인수 값이 범위보다 크거나 음수이면 저장된 다른 값들도 이에 따라 수정됩니다.  예를 들어 150초로 지정하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 2분 30초로 다시 정의합니다.  
  
 날짜를 받아들이는 `Date.UTC` 함수와 `Date` 개체 생성자 사이의 차이점은 `Date.UTC` 함수는 UTC로 간주하고 `Date` 개체 생성자는 현지 시간으로 간주한다는 것입니다.  
  
## 예제  
 다음 예제에서는 `Date.UTC` 함수를 사용하는 방법을 보여 줍니다  
  
```javascript  
// Determine the milliseconds per day.  
 var MinMilli = 1000 * 60;  
var HrMilli = MinMilli * 60;  
var DyMilli = HrMilli * 24;  
  
var date = new Date("June 1, 1990");  
var year = date.getFullYear();  
var month = date.getMonth();  
var day = date.getDay();  
  
var newDay = new Date("January 16, 2020");  
var yeartoday = newDay.getUTCFullYear();  
var monthtoday = newDay.getUTCMonth();  
var dayofmonthtoday = newDay.getUTCDate();  
  
// Get the milliseconds since 1/1/1970 UTC.  
var t1 = Date.UTC(year, month - 1, day)  
var t2 = Date.UTC(yeartoday, monthtoday, dayofmonthtoday);  
  
// Determine the difference in days.  
var days = (t2 - t1) / DyMilli;  
  
document.write(days);  
// Output: 10848  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [setTime 메서드\(Date\)](../../javascript/reference/settime-method-date-javascript.md)
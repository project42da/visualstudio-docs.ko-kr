---
title: "Date.UTC 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: UTC
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC function [JavaScript]
- UTC dates, returning
- Date.UTC function [JavaScript]
ms.assetid: c0d67ce1-a47e-4dfd-bbf4-21619c406a0f
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a6a7c5622b74699e3d718ceb65e96638bdb6c3c5
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="dateutc-function-javascript"></a>Date.UTC 함수(JavaScript)
1970 년 1 월 1 일 자정 사이의 밀리초 수를 반환 utc (협정 세계시) 또는 GMT () 및 지정된 된 날짜입니다.  
  
## <a name="syntax"></a>구문  
  
```  
Date.UTC(year, month, day[, hours[, minutes[, seconds[,ms]]]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `year`  
 필수 요소. 세기 날짜 정확도 대 한 필요한은 연도 지정 합니다. 경우 `year` 0과 99 사이의 사용 하는 다음 `year` 1900 것으로 간주 됩니다 + `year`합니다.  
  
 `month`  
 필수 요소. 0과 11 (12 월 1 월) 사이의 정수 월입니다.  
  
 `day`  
 필수 요소. 1에서 31 사이의 정수 날짜입니다.  
  
 `hours`  
 선택 사항입니다. 경우에 제공 해야 `minutes` 를 제공 합니다. 하는 정수 0에서 23 (오후 11 시 자정) 시간을 지정 합니다.  
  
 `minutes`  
 선택 사항입니다. 경우에 제공 해야 `seconds` 를 제공 합니다. 분을 지정 하는 0부터 59 까지의 정수로 합니다.  
  
 `seconds`  
 선택 사항입니다. 경우에 제공 해야 `milliseconds` 를 제공 합니다. 초는 0부터 59 까지의 정수로 합니다.  
  
 `ms`  
 선택 사항입니다. 하는 정수 0에서 999 사이의 밀리초를 지정 합니다.  
  
## <a name="remarks"></a>설명  
 `Date.UTC` 함수 자정, UTC 1970 년 1 월 1 일 및 제공 된 날짜 사이의 밀리초 수를 반환 합니다. 이 반환 값에서 사용할 수는 `setTime` 메서드 및는 `Date` 개체 생성자입니다. 인수 값의 범위 보다 클 음수인 경우 저장 된 다른 값도 수정 됩니다. 예를 들어 150 초로 지정 하면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 다시 정의 합니다 2 분 30 초입니다.  
  
 차이 `Date.UTC` 함수 및 `Date` 는 날짜를 허용 하는 개체 생성자는 `Date.UTC` 함수는 utc로 간주 및 `Date` 개체 생성자에는 현지 시간으로 간주 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Date.UTC` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [setTime 메서드(Date)](../../javascript/reference/settime-method-date-javascript.md)
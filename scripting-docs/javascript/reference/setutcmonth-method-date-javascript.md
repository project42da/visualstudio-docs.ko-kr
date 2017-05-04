---
title: "setUTCMonth 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setUTCMonth"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, UTC"
  - "Month 메서드"
  - "setUTCMonth 메서드"
  - "UTC 날짜, 설정"
ms.assetid: cdac5f64-c4fd-44cc-ba3a-9a8dd3dd3fad
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# setUTCMonth 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 `Date` 개체의 월 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setUTCMonth(numMonth[, dateVal])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numMonth`  
 필수 요소.  월에 해당하는 숫자 값입니다.  1월의 값은 0이고 다른 달 값은 순차적으로 증가합니다.  
  
 `dateVal`  
 선택 사항입니다.  일\(한 달 기준\)을 나타내는 숫자 값입니다.  값을 지정하지 않으면 `getUTCDate` 메서드를 호출하여 받은 값이 사용됩니다.  
  
## 설명  
 현지 시간을 사용하여 월 값을 설정하려면 `setMonth` 메서드를 사용합니다.  
  
 `numMonth`의 값이 11보다 크거나\(January가 0임\) 음수이면 이에 따라 저장된 연도도 증감합니다.  예를 들어 저장된 날짜가 "Jan 5, 1996 00:00:00.00"이고 **setUTCMonth\(14\)**가 호출되면 날짜는 "Mar 5, 1997 00:00:00.00"으로 바뀝니다.  
  
 **setUTCFullYear** 메서드를 사용하여 년, 월, 일을 설정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `setUTCMonth` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetUTCMonthDemo(newmonth){  
   var d, s;                       // Declare variables.  
   d = new Date();                 // Create Date object.  
   d.setUTCMonth(newmonth);        // Set UTC month.  
   s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                      // Return new setting.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMonth 메서드\(Date\)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth 메서드\(Date\)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth 메서드\(Date\)](../../javascript/reference/setmonth-method-date-javascript.md)
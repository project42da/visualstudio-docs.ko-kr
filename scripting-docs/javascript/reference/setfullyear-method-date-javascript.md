---
title: "setFullYear 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setFullYear"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Year 메서드"
  - "setFullYear 메서드"
  - "날짜, 설정"
ms.assetid: 635e4f5a-0210-4c01-8152-b0da4146f6ff
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# setFullYear 메서드(Date)(JavaScript)
설정의 연도 `Date` 로컬 시간을 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.setFullYear(numYear[, numMonth[, numDate]])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numYear`  
 필수 요소.  연도 숫자 값입니다.  
  
 `numMonth`  
 선택적 요소.  \(0 1 월 11 년 12 월에 대 한\) 월부터 숫자 값입니다.  지정 해야 `numDate` 지정 된.  
  
 `numDate`  
 선택적 요소.  같은 달의 날짜에는 숫자 값입니다.  
  
## 설명  
 선택적인 인수를 갖는 모든 **set** 메서드들은 선택적인 인수를 지정하지 않으면 이에 해당하는 **get** 메서드에서 반환된 값을 사용합니다.  예를 들어, 경우는 `numMonth` 인수는 선택 사항 이지만 지정 되지 않음 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하는  **getMonth** 메서드.  
  
 또한 인수 값이 일정 범위 보다 크거나 또는 음수인 경우 날짜 앞 이나 뒤로 적절 하 게 세분화 합니다.  
  
 협정 세계 표준시 \(UTC\)를 사용 하 여 연도 설정할 수 있는 `setUTCFullYear` 메서드.  
  
 Date 개체가 지 원하는 연도 범위는 약 285616 년 1970 전후입니다.  
  
## 예제  
 다음 예제는 `setFullYear` 메서드의 사용 예를 보여 줍니다.  
  
```javascript  
var date1 = new Date("1/1/2001");  
date1.setFullYear(2007);  
  
var date2 = new Date("1/1/2001");  
date2.setFullYear(2008, 10, 3);   
  
document.write (date1.toLocaleString());  
document.write ("<br />");  
document.write (date2.toLocaleString());  
  
// Output:  
// Monday, January 01, 2007 12:00:00 AM  
// Monday, November 03, 2008 12:00:00 AM  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getFullYear 메서드\(Date\)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드\(Date\)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드\(Date\)](../../javascript/reference/setutcfullyear-method-date-javascript.md)
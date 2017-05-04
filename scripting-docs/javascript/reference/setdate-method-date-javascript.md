---
title: "setDate 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setDate"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "setDate 메서드"
  - "날짜, 설정"
ms.assetid: a84b9b01-a6d0-489f-8a13-e7af9e9630b2
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# setDate 메서드(Date)(JavaScript)
일 월 숫자 값을 설정 하는 `Date` 로컬 시간을 사용 하 여 개체.  
  
## 구문  
  
```  
  
dateObj.setDate(numDate)   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numDate`  
 필수 요소.  일\(한 달 기준\)에 해당하는 숫자 값입니다.  
  
## 설명  
 협정 세계 표준시 \(UTC\)를 사용 하 여 일 월 값을 설정 하려면 사용 하는 `setUTCDate` 메서드.  
  
 경우의 값은 `numDate` 일 위에 날짜 롤 나중에 달 또는 연도에 있는 월 수보다 큽니다.  예를 들어, 저장 된 날짜가 1996 년 1 월 5 일 및 `setDate(32)` 이라고, 1996 년 2 월 1 일 날짜 변경 합니다.  경우 `numDate` 음수 값은 이전 달 또는 연도에 다시 날짜 롤입니다.  예를 들어, 저장 된 날짜가 1996 년 1 월 5 일 및 `setDate(-32)` 이라고, 1995 년 11 월 29 일 날짜 변경 합니다.  
  
 [setFullYear 메서드\(Date\)](../../javascript/reference/setfullyear-method-date-javascript.md) 연도, 월, 일을 설정 하는 데 사용 합니다.  
  
## 예제  
 다음 예제에서는 `setDate` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date("12/15/1990");  
date.setDate(30);  
document.write(date);  
  
// Output (for the PST time zone): Sun Dec 30 00:00:00 PST 1990  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getDate 메서드\(Date\)](../../javascript/reference/getdate-method-date-javascript.md)   
 [setFullYear 메서드\(Date\)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setMonth 메서드\(Date\)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCDate 메서드\(Date\)](../../javascript/reference/setutcdate-method-date-javascript.md)
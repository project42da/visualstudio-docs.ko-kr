---
title: "Date.parse 함수(JavaScript) | Microsoft Docs"
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
  - "parse"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date.parse 함수[JavaScript]"
  - "parse 함수[JavaScript]"
ms.assetid: ed737e50-6398-4462-8779-2af3c03f8325
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# Date.parse 함수(JavaScript)
날짜를 포함한 문자열 구문을 분석하여 1970년 1월 1일 자정부터 해당 날짜 사이의 시간을 밀리초로 반환합니다.  
  
## 구문  
  
```  
Date.parse(dateVal)   
```  
  
## 설명  
 필수 `dateVal` 인수는 날짜가 포함된 문자열 또는 ActiveX 개체나 다른 개체에서 검색된 VT\_DATE 값입니다.  `Date.parse` 함수가 구문 분석할 수 있는 날짜 문자열에 대한 자세한 내용은 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)을 참조하십시오.  
  
 `Date.parse` 함수는 1970년 1월 1일 자정과 `dateVal`에 지정된 날짜 사이의 시간을 밀리초 단위로 나타내는 정수 값을 반환합니다.  
  
## 예제  
 다음 예제에서는 `Date.parse` 함수의 사용법을 보여 줍니다.  
  
```javascript  
var dateString = "November 1, 1997 10:15 AM";  
var mSec = Date.parse(dateString);  
document.write(mSec);  
// Output: 878404500000  
```  
  
## 예제  
 다음 예제에서는 제공된 날짜와 1\/1\/1970 사이의 차이를 반환합니다.  
  
```javascript  
var minMilli = 1000 * 60;  
var hrMilli = minMilli * 60;  
var dyMilli = hrMilli * 24;  
  
var testDate = new Date("June 1, 1990");  
var ms = Date.parse(testDate);  
var days = Math.round(ms / dyMilli);  
  
var dateStr = "";  
dateStr += "There are " + days + " days ";  
dateStr += "between 01/01/1970 and " + testDate;  
document.write(dateStr);  
  
// Output: There are 7456 days between 01/01/1970 and Fri Jun 1 00:00:00 PDT 1990  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [getDate 메서드\(Date\)](../../javascript/reference/getdate-method-date-javascript.md)
---
title: "format 속성(Intl.DateTimeFormat) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 487930fe-a948-446f-902d-06bb0d7685d5
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# format 속성(Intl.DateTimeFormat)
지정된 날짜\/시간 포맷터 설정을 사용해서 로캘별 날짜 형식을 지정하는 함수를 반환합니다.  
  
## 구문  
  
```  
dateTimeFormatObj.format  
```  
  
#### 매개 변수  
 `dateTimeFormatObj`  
 필수 요소.  포맷터로 사용할 `DateTimeFormat` 개체의 이름입니다.  
  
## 설명  
 `format` 속성에서 반환되는 함수에는 `date`라는 인수 한 개가 있고 `DateTimeFormat` 개체에 지정된 옵션을 사용하여 지역화된 날짜를 표현하는 문자열을 반환합니다.  반환된 함수의 `date` 매개 변수는 숫자, 날짜 문자열 또는 `Date` 개체여야 합니다.  `date`가 제공되지 않는 경우 함수는 [Date.now](../../javascript/reference/date-now-function-javascript.md)를 기본 입력 값으로 사용합니다.  
  
## 예제  
 다음 예제에서는 `DateTimeFormat` 개체를 사용하여 날짜 "Dec 1, 2007"을 독일어로 지역화하고 서식을 다시 지정합니다.  
  
```javascript  
var dtFormat = new Intl.DateTimeFormat(["de"], {  
    year: "numeric",  
    month: "long",  
    day: "2-digit",  
    hour: "numeric"  
});  
  
if (console && console.log) {  
    console.log(dtFormat.format(new Date("Dec 1, 2007")));  
    // Returns 01. Dezember 2007 00:00  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [Intl.DateTimeFormat 개체](../../javascript/reference/intl-datetimeformat-object-javascript.md)
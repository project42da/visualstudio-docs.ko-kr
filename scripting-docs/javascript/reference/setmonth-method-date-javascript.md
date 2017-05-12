---
title: "setMonth 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setMonth"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Month 메서드"
  - "setMonth 메서드"
ms.assetid: 4f5be295-d536-46c0-b3a4-ad06457efe82
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# setMonth 메서드(Date)(JavaScript)
현지 시간을 사용하여 `Date` 개체의 월 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj. setMonth(numMonth[, dateVal])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numMonth`  
 필수 요소.  월에 해당하는 숫자 값입니다.  1월의 값은 0이고 다른 달 값은 순차적으로 증가합니다.  
  
 `dateVal`  
 선택 사항입니다.  일\(한 달 기준\)을 나타내는 숫자 값입니다.  이 값을 부여하지 않으면 `getDate` 메서드를 호출하여 받은 값을 사용합니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 월 값을 설정하려면 `setUTCMonth` 메서드를 사용하세요.  
  
 `numMonth`의 값이 11보다 크거나\(January는 0임\) 음수이면 이에 따라 저장된 다른 값들도 변경됩니다.  예를 들어 저장된 날짜가 "Jan 5, 1996"이고 **setMonth\(14\)**가 호출되면 날짜는 "Mar 5, 1997"로 바뀝니다.  
  
 **setFullYear** 메서드를 사용하여 년, 월 및 일\(한 달 기준\)을 설정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `setMonth` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
date = new Date('1/1/1990');  
date.setMonth(14);  
document.write(date);  
  
// Output: Fri Mar 1 00:00:00 PST 1991  
// Note that the time zone corresponds to the time zone on the local computer.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMonth 메서드\(Date\)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth 메서드\(Date\)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setUTCMonth 메서드\(Date\)](../../javascript/reference/setutcmonth-method-date-javascript.md)
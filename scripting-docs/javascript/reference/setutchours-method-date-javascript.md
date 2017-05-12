---
title: "setUTCHours 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setUTCHours"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, UTC"
  - "setUTCHours 메서드"
  - "UTC 시간, 설정"
ms.assetid: 257e36fd-fb06-4a4d-8634-d66a020a1511
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# setUTCHours 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 `Date` 개체의 시 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setUTCHours(numHours[, numMin[, numSec[, numMilli]]])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numHours`  
 필수 요소.  시 값에 해당하는 숫자 값입니다.  
  
 `numMin`  
 선택 사항입니다.  분 값에 해당하는 숫자 값입니다.  `numSec` 또는 `numMilli`를 사용하는 경우 제공해야 합니다.  
  
 `numSec`  
 선택 사항입니다.  초 값에 해당하는 숫자 값입니다.  `numMilli` 인수를 사용하는 경우 제공해야 합니다.  
  
 `numMilli`  
 선택 사항입니다.  밀리초 값에 해당하는 숫자 값입니다.  
  
## 설명  
 선택적 인수를 지정하지 않으면 선택적 인수를 갖는 모든 **set** 메서드는 해당 **get** 메서드에서 반환된 값을 사용합니다.  예를 들어 `numMin` 인수를 지정하지 않은 경우 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 `getUTCMinutes` 메서드에서 반환된 값을 사용합니다.  
  
 현지 시간을 사용하여 시간 값을 설정하려면 `setHours` 메서드를 사용하세요.  
  
 인수 값이 범위보다 크거나 음수이면 저장된 다른 값들도 이에 따라 수정됩니다.  예를 들어 저장된 날짜가 "Jan 5, 1996 00:00:00.00"이고 **setUTCHours\(30\)**가 호출되면 날짜는 "Jan 6, 1996 06:00:00.00"으로 바뀝니다.  
  
## 예제  
 다음 예제에서는 `setUTCHours` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetUTCHoursDemo(nhr, nmin, nsec){     
   var d, s;                        // Declare variables.  
   d = new Date();                  // Create Date object.  
   d.setUTCHours(nhr, nmin, nsec);  // Set UTC hours, minutes, seconds.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                       // Return new setting.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getHours 메서드\(Date\)](../../javascript/reference/gethours-method-date-javascript.md)   
 [getUTCHours 메서드\(Date\)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours 메서드\(Date\)](../../javascript/reference/sethours-method-date-javascript.md)
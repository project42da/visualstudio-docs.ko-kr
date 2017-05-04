---
title: "setUTCSeconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setUTCSeconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, UTC"
  - "seconds 메서드"
  - "setUTCSeconds 메서드"
  - "UTC 시간, 설정"
ms.assetid: e035e282-b39d-4d1d-8771-c17542fd6493
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# setUTCSeconds 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 `Date` 개체의 초 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setUTCSeconds(numSeconds[, numMilli])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 *numSeconds*  
 필수 요소.  초 값에 해당하는 숫자 값입니다.  
  
 `numMilli`  
 선택 사항입니다.  밀리초 값에 해당하는 숫자 값입니다.  
  
## 설명  
 선택적 인수를 지정하지 않으면 선택적 인수를 갖는 모든 **set** 메서드는 해당 **get** 메서드에서 반환된 값을 사용합니다.  예를 들어 `numMilli` 인수를 지정하지 않은 경우 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 `getUTCMilliseconds` 메서드에서 반환된 값을 사용합니다.  
  
 현지 시간을 사용하여 초 값을 설정하려면 `setSeconds` 메서드를 사용합니다.  
  
 인수 값이 범위보다 크거나 음수이면 저장된 다른 값들도 이에 따라 수정됩니다.  예를 들어 저장된 날짜가 "Jan 5, 1996 00:00:00.00"이고 **setSeconds\(150\)**를 호출하면 날짜가 "Jan 5, 1996 00:02:30.00"으로 바뀝니다.  
  
 **setUTCHours** 메서드를 사용하여 시, 분, 초 및 밀리초를 설정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `setUTCSeconds` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetUTCSecondsDemo(nsec){  
// Create Date object.  
    var d = new Date();       
// Set UTC seconds.  
    d.setUTCSeconds(nsec);    
    var s = "Current setting is ";  
    s += d.toUTCString();  
// Return new setting.  
    return(s);                
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getSeconds 메서드\(Date\)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [getUTCSeconds 메서드\(Date\)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds 메서드\(Date\)](../../javascript/reference/setseconds-method-date-javascript.md)
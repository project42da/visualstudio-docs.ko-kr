---
title: "setMinutes 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setMinutes"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "분"
  - "setMinutes 메서드"
ms.assetid: 34c959cd-cd29-4cee-8e04-9061cf6d42f3
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# setMinutes 메서드(Date)(JavaScript)
현지 시간을 사용하여 **Date** 개체의 분 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numMinutes`  
 필수 요소.  분 값에 해당하는 숫자 값입니다.  다음 인수 중 하나를 사용하는 경우 반드시 사용해야 합니다.  
  
 *numSeconds*  
 선택 사항입니다.  초 값에 해당하는 숫자 값입니다.  `numMilli` 인수를 사용하는 경우 제공해야 합니다.  
  
 `numMilli`  
 선택 사항입니다.  밀리초 값에 해당하는 숫자 값입니다.  
  
## 설명  
 선택적 인수를 지정하지 않으면 선택적 인수를 갖는 모든 **set** 메서드는 해당 **get** 메서드에서 반환된 값을 사용합니다.  예를 들어 *numSeconds* 인수를 지정하지 않으면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 `getSeconds` 메서드에서 반환된 값을 사용합니다.  
  
 UTC\(협정 세계 표준시\)를 사용하여 분 값을 설정하려면 `setUTCMinutes` 메서드를 사용하세요.  
  
 인수 값이 범위보다 크거나 음수이면 저장된 다른 값들도 이에 따라 수정됩니다.  예를 들어 저장된 날짜가 "Jan 5, 1996 00:00:00"이고 **setMinutes\(90\)**가 호출되면 날짜는 "Jan 5, 1996 01:30:00"으로 바뀝니다. 음수 값도 같은 방법으로 처리됩니다.  
  
## 예제  
 다음 예제에서는 `setMinutes` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetMinutesDemo(nmin, nsec){  
   var d, s;                     // Declare variables.  
   d = new Date();               // Create Date object.  
   d.setMinutes(nmin, nsec);     // Set minutes.  
   s = "Current setting is " + d.toLocaleString()   
   return(s);                    // Return new setting.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMinutes 메서드\(Date\)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes 메서드\(Date\)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setUTCMinutes 메서드\(Date\)](../../javascript/reference/setutcminutes-method-date-javascript.md)
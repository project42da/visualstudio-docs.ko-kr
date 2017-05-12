---
title: "setUTCDate 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setUTCDate"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, 설정"
  - "날짜, UTC"
  - "setUTCDate 메서드"
  - "UTC 날짜, 설정"
ms.assetid: e6c3b876-70fe-4103-b197-6c84c078ce10
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# setUTCDate 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 `Date` 개체의 날짜\(숫자\)를 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setUTCDate(numDate)   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 *numDate*  
 필수 요소.  일\(한 달 기준\)에 해당하는 숫자 값입니다.  
  
## 설명  
 현지 시간을 사용하여 날짜를 설정하려면 `setDate` 메서드를 사용합니다.  
  
 *numDate*의 값이 **Date**  개체에 저장된 날짜 값보다 크거나 음수이면 *numDate*의 값에서 저장된 날짜 값을 뺀 수를 날짜로 설정합니다.  예를 들어 저장된 날짜가 January 5, 1996이고 **setUTCDate\(32\)**를 호출하면 날짜가 February 1, 1996으로 바뀝니다.  음수 값도 같은 방법으로 처리됩니다.  
  
 **setUTCFullYear** 메서드를 사용하여 년, 월, 일을 설정할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `setUTCDate` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetUTCDateDemo(newdayofmonth){  
   var d = new Date();           // Create Date object.  
   d.setUTCDate(newdayofmonth);  // Set UTC day of month.  
   var s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                    // Return new setting.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getDate 메서드\(Date\)](../../javascript/reference/getdate-method-date-javascript.md)   
 [getUTCDate 메서드\(Date\)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate 메서드\(Date\)](../../javascript/reference/setdate-method-date-javascript.md)
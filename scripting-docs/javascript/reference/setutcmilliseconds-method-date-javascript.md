---
title: "setUTCMilliseconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setUTCMilliseconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, UTC"
  - "밀리초"
  - "setUTCMilliseconds 메서드"
  - "UTC 시간, 설정"
ms.assetid: ed8e4486-d4b2-4b73-836b-dd1d3bb991a0
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# setUTCMilliseconds 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 `Date` 개체의 밀리초 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setUTCMilliseconds(numMilli)   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numMilli`  
 필수 요소.  밀리초 값에 해당하는 숫자 값입니다.  
  
## 설명  
 현지 시간을 사용하여 밀리초를 설정하려면 `setMilliseconds` 메서드를 사용하세요.  
  
 `numMilli` 값이 999보다 크거나 음수이면 저장된 초\(분, 시, 기타 필요한 것\) 값은 이에 따라 적당한 양만큼 증감합니다.  
  
## 예제  
 다음 예제에서는 `setUTCMilliseconds` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetUTCMSecDemo(nmsec){     
// Create Date object.  
   var d = new Date();             
// Set UTC milliseconds.  
   d.setUTCMilliseconds(nmsec);    
  
   var s = "Current setting is ";  
   s += d.toUTCString();  
   s += " and " + d.getUTCMilliseconds();  
   s += " milliseconds"  
   return(s);  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMilliseconds 메서드\(Date\)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [getUTCMilliseconds 메서드\(Date\)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setMilliseconds 메서드\(Date\)](../../javascript/reference/setmilliseconds-method-date-javascript.md)
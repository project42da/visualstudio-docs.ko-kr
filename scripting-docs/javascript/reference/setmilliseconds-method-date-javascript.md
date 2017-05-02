---
title: "setMilliseconds 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setMilliseconds"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "밀리초"
  - "setMilliseconds 메서드"
ms.assetid: 6c398961-130e-4f60-802f-6c30e1ef4de4
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# setMilliseconds 메서드(Date)(JavaScript)
현지 시간을 사용하여 `Date` 개체의 밀리초 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.  
setMilliseconds(  
numMilli  
)   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 `numMilli`  
 필수 요소.  밀리초 값에 해당하는 숫자 값입니다.  
  
## 설명  
 UTC\(협정 세계 표준시\)를 사용하여 밀리초 값을 설정하려면 `setUTCMilliseconds` 메서드를 사용하세요.  
  
 `numMilli` 값이 999보다 크거나 음수이면 저장된 초\(분, 시, 기타 필요한 것\) 값은 이에 따라 적당한 양만큼 증감합니다.  
  
## 예제  
 다음 예제에서는 `setMilliseconds` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetMSecDemo(nmsec){  
   var d, s;                    // Declare variables.  
   d = new Date();              // Create Date object.  
   d.setMilliseconds(nmsec);    // Set milliseconds.  
   s = "Current setting is ";  
   s += d.toLocaleString();  
   s += " and " + d.getMilliseconds();  
   s += " milliseconds";  
   return(s);                   // Return new date setting.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getMilliseconds 메서드\(Date\)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [getUTCMilliseconds 메서드\(Date\)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds 메서드\(Date\)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)
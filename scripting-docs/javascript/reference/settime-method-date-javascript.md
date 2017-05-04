---
title: "setTime 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "setTime"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "SetTime 메서드"
  - "time 메서드"
ms.assetid: 86584748-7219-495b-bf56-e27f5782778c
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# setTime 메서드(Date)(JavaScript)
`Date` 개체의 날짜와 시간 값을 설정합니다.  
  
## 구문  
  
```  
  
dateObj.setTime(milliseconds)   
```  
  
## 매개 변수  
 `dateObj`  
 필수 요소.  임의의 `Date` 개체입니다.  
  
 *milliseconds*  
 필수 요소.  GMT 1970년 1월 1일 자정부터 경과된 시간을 밀리초로 나타낸 숫자 값입니다.  
  
## 설명  
 *milliseconds*가 음수이면 1970년 이전의 날짜를 나타냅니다.  사용 가능한 날짜 범위는 1970년을 전후로 약 285,616년까지입니다.  
  
 `setTime` 메서드로 설정한 날짜와 시간은 기준 시간대와는 다릅니다.  
  
## 예제  
 다음 예제에서는 `setTime` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function SetTimeTest(newtime){  
   var d, s;                  //Declare variables.  
   d = new Date();            //Create Date object.  
   d.setTime(newtime);        //Set time.  
   s = "Current setting is ";  
   s += d.toUTCString();  
   return(s);                 //Return new setting.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getTime 메서드\(Date\)](../../javascript/reference/gettime-method-date-javascript.md)
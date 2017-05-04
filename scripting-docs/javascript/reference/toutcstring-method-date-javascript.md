---
title: "toUTCString 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "toUTCString"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toUTCString 메서드"
  - "UTC 날짜, 문자열로 변환"
ms.assetid: eb0983ed-7884-42fa-a2cc-de92b3111207
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# toUTCString 메서드(Date)(JavaScript)
UTC\(협정 세계 표준시\)를 사용하여 문자열로 변환된 날짜를 반환합니다.  
  
## 구문  
  
```  
  
dateObj.toUTCString()   
```  
  
## 설명  
 필수 `dateObj` 참조는 임의의 `Date` 개체입니다.  
  
 `toUTCString` 메서드는 UTC 규칙을 사용하는 날짜 형식을 가진 `String` 개체를 편리하고 읽기 쉬운 형식으로 반환합니다.  
  
## 예제  
 다음 예제에서는 `toUTCString` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function toUTCStrDemo(){  
   var d, s;                   //Declare variables.  
   d = new Date();             //Create Date object.  
   s = "Current setting is ";  
   s += d.toUTCString();       //Convert to UTC string.  
   return(s);                  //Return UTC string.  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [toGMTString 메서드\(Date\)](../../javascript/reference/togmtstring-method-date-javascript.md)